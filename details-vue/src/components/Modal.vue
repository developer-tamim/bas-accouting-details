<template>
    <transition name="slide-down">
      <div v-if="isVisible" class="modal-overlay">
        <div class="modal-content">
          
          <!-- top section (modal header) -->
          <div class="d-flex justify-content-between align-items-center bg-secondary text-light p-2">
            <span style="font-weight: 700; font-size: 20px;">Details</span>
            <button @click="closeModal" class="btn btn-secondary">Close</button>
          </div>
  
          <!-- header section -->
          <div class="d-flex justify-content-between mb-5 mt-4">
            <div class="d-flex flex-column align-items-end">
              <span style="color: #2F415E; font-weight: 700; font-size: 20px;">Check: 0000123456879</span>
              <span style="color: #2F415E; font-size: 20px;">Receive Date: 02/26/2024</span>
            </div>
  
            <div class="d-flex flex-column align-items-end">
              <span style="color: #2F415E; font-weight: 700;">Customer Balance</span>
              <span style="color: #2F415E; font-weight: 600;">$ 1,234.00</span>
            </div>
          </div>
  
          <!-- AMC name section -->
          <div class="d-flex justify-content-between mt-5">
            <div class="d-flex flex-column align-items-start">
              <span style="color: #2F415E; font-weight: 700; width: 218px;">AMC Name</span>
              <select class="form-select">
                <option value="check">Desktop Appraisal</option>
                <option value="direct_deposit">Value Net</option>
              </select>
            </div>
  
            <div class="d-flex flex-column align-items-end">
              <span style="color: #2F415E; font-weight: 700; font-size: 20px;">Amount Received</span>
              <input class="form-control font-weight-bold" type="text" v-model="totalReceived" />
            </div>
          </div>
  
          <!-- payment methods section -->
          <div class="d-flex justify-content-between mt-4">
            <div class="d-flex flex-column align-items-start">
              <span style="color: #2F415E; font-weight: 700; width: 218px;">Payment Methods</span>
              <select class="form-select">
                <option value="check">Check</option>
                <option value="direct_deposit">Direct Deposit</option>
              </select>
            </div>
  
            <div class="d-flex flex-column align-items-start">
              <span style="color: #2F415E; font-weight: 700; width: 218px;">Deposit To</span>
              <select class="form-select">
                <option value="bank_of_america">Bank of America</option>
                <option value="eastern_bank">Eastern Bank</option>
                <option value="bank_of_asia">Bank of Asia</option>
              </select>
            </div>
  
            <div class="d-flex flex-column align-items-start">
              <span style="color: #2F415E;">Search</span>
              <input class="form-control" placeholder="Search..." type="text" />
            </div>
          </div>
  
          <!-- table -->
          <div class="table-responsive mt-4">
            <table class="table">
              <thead>
                <tr>
                  <th><input type="checkbox" /></th>
                  <th>Order No.</th>
                  <th>Property Address</th>
                  <th>Due Date</th>
                  <th>Original Balance</th>
                  <th>Open Balance</th>
                  <th>Payment</th>
                  <th>Action</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in tableData" :key="item.id">
                  <td><input type="checkbox" v-model="item.isChecked" /></td>
                  <td>{{ item.orderNo }}</td>
                  <td>{{ item.propertyAddress }}</td>
                  <td>{{ item.dueDate }}</td>
                  <td>{{ item.originalBalance }}</td>
                  <td>{{ item.openBalance }}</td>
                  <td>$ <input type="number" style="border:none" v-model="item.payment" @input="updateTotalReceived" /></td>
                  <td><button @click="processAction(item)">Process</button></td>
                </tr>
              </tbody>
            </table>
          </div>
  
          <!-- pagination -->
          <div class="d-flex justify-content-center mb-4">
            <div class="pagination">
              <a href="#">&laquo;</a>
              <a href="#">1</a>
              <a href="#">2</a>
              <a href="#">3</a>
              <a href="#">4</a>
              <a href="#">5</a>
              <a href="#">6</a>
              <a href="#">&raquo;</a>
            </div>
          </div>
          <!-- pagination -->
        </div>
      </div>
    </transition>
  </template>
  
  <script>
  import { ref, computed } from 'vue';
  
  export default {
    props: {
      isVisible: {
        type: Boolean,
        required: true,
      },
    },
    setup(props, { emit }) {
      const closeModal = () => {
        emit('close');
      };
  
      const tableData = ref([
        {
          id: 1,
          isChecked: false,
          orderNo: 'BAS-123456789',
          propertyAddress: '104 Mount Auborn Street',
          dueDate: '02/26/2024',
          originalBalance: '$ 1500.00',
          openBalance: '$ 1500.00',
          payment: 1500.00,
        },
        {
          id: 2,
          isChecked: false,
          orderNo: 'BAS-987654321',
          propertyAddress: '210 Elm Street',
          dueDate: '03/15/2024',
          originalBalance: '$ 2000.00',
          openBalance: '$ 2000.00',
          payment: 2000.00,
        },
      ]);
  
      const totalReceived = computed(() => {
        let total = 0;
        tableData.value.forEach(item => {
          total += parseFloat(item.payment);
        });
        return total.toFixed(2); // Format as currency or desired precision
      });
  
      const processAction = (item) => {
        // Add your logic to process the action here
        console.log('Processing action...', item);
      };
  
      const updateTotalReceived = () => {
        // No need for implementation here, computed property handles total calculation
      };
  
      return { closeModal, tableData, totalReceived, processAction, updateTotalReceived };
    },
  };
  </script>
  
  <style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: flex-start;
    justify-content: center;
  }
  
  .modal-content {
    background: white;
    padding: 20px;
    border-radius: 5px;
    margin-top: 20px; /* Adjust this value as needed */
    transition: transform 0.3s ease-out;
  }
  
  /* Add the transition effect */
  .slide-down-enter-active, .slide-down-leave-active {
    transition: opacity 0.3s, transform 0.3s;
  }
  
  .slide-down-enter, .slide-down-leave-to {
    opacity: 0;
    transform: translateY(-100%);
  }
  </style>
  