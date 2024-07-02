<template>
  <transition name="slide-down">
    <div v-if="isVisible" class="modal-overlay">
      <div class="modal-content">
        <!-- top section (modal header) -->
        <div
          class="bg text-light d-flex justify-content-between align-items-center px-0 px-md-4"
        >
          <span class="fs-25 fw-700">Details</span>
          <i
            @click="closeModal"
            class="fa-solid fa-xmark fs-25 fw-700"
          ></i>
        </div>

        <!-- header section -->
        <div class="container my-3 px-4">
          <div class="row mb-3">
            <div class="col-12 col-md-6">
              <div class="text-color fw-700 fs-20">
                Check: 00001321564687
              </div>
              <div class="fs-18">Received Date: mm / dd / yyyy</div>
            </div>
            <div
              class="col-12 col-md-6 text-md-end mt-2 text-start text-md-end"
            >
              <div class="fw-700 fs-16">
                Customer Balance
              </div>
              <div class="fw-700 fs-21">$1,234.00</div>
            </div>
          </div>

          <!-- amount received section -->
          <div class="row mb-3">
            <div
              class="col-12 col-md-6 offset-md-6 d-flex flex-column align-items-md-end align-items-start"
            >
              <div class="fw-700 fs-18">
                Amount Received
              </div>
              <div>
                <input
                  
                    width="142px"
                    height="39px"
                  
                  class="text-end form-control fw-700 fs-23" 
                  type="number"
                  v-model="totalReceived"
                />
              </div>
            </div>
          </div>

          <!-- AMC name section -->
          <div class="d-flex flex-column align-items-start">
            <span class="text-color fw-700 fs-18" width="218"
              >AMC Name</span
            >
            <select class="form-select w-220">
              <option value="">Value Net</option>
              <option value="">Deskto Appraisal</option>
              <option value="">123456</option>
            </select>
          </div>

          <!-- payment methods section -->
          <!-- Responsive row -->
          <div class="row my-3">
            <div class="col-12 col-md-4 mb-3 mb-md-0">
              <div class="d-flex flex-column align-items-start">
                <span class="text-color fw-700 fs-18" width="218">Payment Methods</span>
                <select class="form-select" width="100%">
                  <option value="check">Check</option>
                  <option value="direct_deposit">Direct Deposit</option>
                </select>
              </div>
            </div>

            <div class="col-12 col-md-4 mb-3 mb-md-0">
              <div class="d-flex flex-column align-items-start">
                <span class="text-color fw-700 fs-18" width="218"
                  >Deposit To</span
                >
                <select class="form-select" width="100%">
                  <option value="bank_of_america">Bank of America</option>
                  <option value="eastern_bank">Eastern Bank</option>
                  <option value="bank_of_asia">Bank of Asia</option>
                </select>
              </div>
            </div>

            <div class="col-12 col-md-4">
              <div class="d-flex flex-column align-items-start">
                <span class="text-color">Search</span>
                <input
                  class="form-control"
                  placeholder="Search..."
                  type="text"
                  width="100%"
                />
              </div>
            </div>
          </div>
          <!-- End responsive row -->
          <!-- payment methods section -->

          <!-- table start -->
          <div class="table-responsive">
            <table class="table table-striped mt-4">
              <thead>
                <tr>
                  <th><input type="checkbox" /></th>
                  <th class="text-color">Order No.</th>
                  <th class="text-color">Property Address</th>
                  <th class="text-color">Due Date</th>
                  <th class="text-color">Original Balance</th>
                  <th class="text-color">Open Balance</th>
                  <th class="text-color">Payment</th>
                  <th class="text-color">Action</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td class="align-middle"><input type="checkbox" /></td>
                  <td class="align-middle">BAS-132456789</td>
                  <td class="align-middle">104 Mount Auborn Street</td>
                  <td class="align-middle">02/26/2024</td>
                  <td class="align-middle">$ 1500.00</td>
                  <td class="align-middle">$ 1500.00</td>

                  <td class="align-middle">
                    <input
                      type="text"
                      style="width: 100px"
                      class="form-control payment-input"
                      value="$ 1500.00"
                    />
                  </td>
                  <!-- multiple invoice history edit -->

                  <td class="align-middle">
                    <i class="fa fa-eye"></i>
                  </td>
                </tr>
                <tr>
                  <td class="align-middle"><input type="checkbox" /></td>
                  <td class="align-middle">BAS-132456789</td>
                  <td class="align-middle">104 Mount Auborn Street</td>
                  <td class="align-middle">02/26/2024</td>
                  <td class="align-middle">$ 1500.00</td>
                  <td class="align-middle">$ 1500.00</td>

                  <td class="align-middle">
                    <input
                      type="text"
                      style="width: 100px"
                      class="form-control payment-input"
                      value="$ 1500.00"
                    />
                  </td>
                  <!-- multiple invoice history edit -->

                  <td class="align-middle">
                    <i class="fa fa-eye"></i>
                  </td>
                </tr>
                <tr>
                  <td class="align-middle"><input type="checkbox" /></td>
                  <td class="align-middle">BAS-132456789</td>
                  <td class="align-middle">104 Mount Auborn Street</td>
                  <td class="align-middle">02/26/2024</td>
                  <td class="align-middle">$ 1500.00</td>
                  <td class="align-middle">$ 1500.00</td>

                  <td class="align-middle">
                    <input
                      type="text"
                      style="width: 100px"
                      class="form-control payment-input"
                      value="$ 1500.00"
                    />
                  </td>
                  <!-- multiple invoice history edit -->

                  <td class="align-middle">
                    <i class="fa fa-eye"></i>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
          <!-- table end -->

          <!-- pagination start -->
          <nav aria-label="Page navigation example">
            <ul class="pagination justify-content-center">
              <li class="page-item disabled">
                <a class="page-link">Previous</a>
              </li>
              <li class="page-item"><a class="page-link" href="#">1</a></li>
              <li class="page-item"><a class="page-link" href="#">2</a></li>
              <li class="page-item"><a class="page-link" href="#">3</a></li>
              <li class="page-item">
                <a class="page-link" href="#">Next</a>
              </li>
            </ul>
          </nav>
          <!-- pagination end -->

          <!-- footer start -->
          <div class="row mb-3">
            <div class="col-12 col-md-5">
              <div class="mb-3 mb-md-0">
                <div class="fw-700 fs-20">Memo</div>
                <div>
                  <textarea rows="4" class="form-control"></textarea>
                </div>
              </div>
            </div>

            <div class="col-md-2"></div>

            <div class="col-12 col-md-5">
              <div class="row">
                <div class="col-6 mb-3 mb-md-0">
                  <div class="mb-2 fs-20 fw-600">
                    Amount to Apply
                  </div>
                  <div class="fs-20 fw-600">
                    Amount to Credit
                  </div>
                </div>
                <div class="col-6">
                  <div class="d-flex justify-content-end align-items-end flex-column">
                    <div class="mb-2 fs-20 fw-600">
                      $ 300.00
                    </div>
                    <div class="fs-20 fw-600">
                      $ 0.00
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <!-- footer end -->

          <div class="d-flex justify-content-end mt-3">
            <button class="rounded-5 py-2 px-3 fs-20 fw-600 bg-white">
              Clear Payment
            </button>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
import { ref, computed } from "vue";

export default {
  props: {
    isVisible: {
      type: Boolean,
      required: true,
    },
  },
  setup(props, { emit }) {
    const closeModal = () => {
      emit("close");
    };

    const tableData = ref([
      {
        id: 1,
        isChecked: false,
        orderNo: "BAS-123456789",
        propertyAddress: "104 Mount Auborn Street",
        dueDate: "02/26/2024",
        originalBalance: "$ 1500.00",
        openBalance: "$ 1500.00",
        payment: 1500.0,
      },
      {
        id: 2,
        isChecked: false,
        orderNo: "BAS-987654321",
        propertyAddress: "210 Elm Street",
        dueDate: "03/15/2024",
        originalBalance: "$ 2000.00",
        openBalance: "$ 2000.00",
        payment: 2000.0,
      },
    ]);

    const totalReceived = computed(() => {
      let total = 0;
      tableData.value.forEach((item) => {
        total += parseFloat(item.payment);
      });
      return total.toFixed(2); // Format as currency or desired precision
    });

    const processAction = (item) => {
      // Add your logic to process the action here
      console.log("Processing action...", item);
    };

    const updateTotalReceived = () => {
      // No need for implementation here, computed property handles total calculation
    };

    return {
      closeModal,
      tableData,
      totalReceived,
      processAction,
      updateTotalReceived,
    };
  },
};
</script>

<style scoped>
html {
  font-family: "Montserrat", sans-serif;
  font-optical-sizing: auto;
}
.bg {
  background-color: #7e829b;
  padding: 10px;
  margin-left: -20px;
  margin-right: -20px;
  margin-top: -20px;
}

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
.slide-down-enter-active,
.slide-down-leave-active {
  transition: opacity 0.3s, transform 0.3s;
}

.slide-down-enter,
.slide-down-leave-to {
  opacity: 0;
  transform: translateY(-100%);
}

.fs-25{
  font-size: 25px; 
}
.fs-20{
  font-size: 20px; 
}
.fs-23{
  font-size: 23px; 
}
.fs-21{
  font-size: 21px; 
}
.fs-18{
  font-size: 18px; 
}
.fs-16{
  font-size: 16px; 
}

.text-color{
  color: #2f415e;
}

.fw-700{
  font-weight: 700;
}
.fw-600{
  font-weight: 600;
}
.w-220{
  width: 220px;
}
</style>
