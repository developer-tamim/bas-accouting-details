<template>
  <transition name="slide-down">
    <div v-if="isVisible" class="modal-overlay">
      <div class="modal-content">
        <!-- top section (modal header) -->
        <div
          class="bg text-light d-flex justify-content-between align-items-center px-0 px-md-4"
        >
          <span style="font-size: 25px; font-weight: 700">Details</span>
          <i
            @click="closeModal"
            class="fa-solid fa-xmark"
            style="font-size: 25px; font-weight: 700"
          ></i>
        </div>

        <!-- header section -->
        <div class="container my-3 px-4">
          <div class="row mb-3">
            <div class="col-12 col-md-6">
              <div style="font-weight: 700; font-size: 20px; color:#2F415E">
                Check: 00001321564687
              </div>
              <div style="font-size: 18px">Received Date: mm / dd / yyyy</div>
            </div>
            <div
              class="col-12 col-md-6 text-md-end mt-2 text-start text-md-end"
            >
              <div style="font-weight: 700; font-size: 16px">
                Customer Balance
              </div>
              <div style="font-weight: 700; font-size: 21px">$1,234.00</div>
            </div>
          </div>

          <!-- amount received section -->
          <div class="row mb-3">
            <div
              class="col-12 col-md-6 offset-md-6 d-flex flex-column align-items-md-end align-items-start"
            >
              <div style="font-weight: 700; font-size: 18px">
                Amount Received
              </div>
              <div>
                <input
                  style="
                    font-weight: 700;
                    font-size: 23px;
                    width: 142px;
                    height: 39px;
                  "
                  class="text-end form-control"
                  type="number"
                  v-model="totalReceived"
                />
              </div>
            </div>
          </div>

          <!-- AMC name section -->
          <div class="d-flex flex-column align-items-start">
            <span style="color: #2f415e; font-weight: 700; width: 218px; font-size: 18px;"
              >AMC Name</span
            >
            <select class="form-select" style="width: 220px">
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
                <span style="color: #2f415e; font-weight: 700; width: 218px; font-size: 18px;"
                  >Payment Methods</span
                >
                <select class="form-select" style="width: 100%">
                  <option value="check">Check</option>
                  <option value="direct_deposit">Direct Deposit</option>
                </select>
              </div>
            </div>

            <div class="col-12 col-md-4 mb-3 mb-md-0">
              <div class="d-flex flex-column align-items-start">
                <span style="color: #2f415e; font-weight: 700; width: 218px; font-size: 18px;"
                  >Deposit To</span
                >
                <select class="form-select" style="width: 100%">
                  <option value="bank_of_america">Bank of America</option>
                  <option value="eastern_bank">Eastern Bank</option>
                  <option value="bank_of_asia">Bank of Asia</option>
                </select>
              </div>
            </div>

            <div class="col-12 col-md-4">
              <div class="d-flex flex-column align-items-start">
                <span style="color: #2f415e">Search</span>
                <input
                  class="form-control"
                  placeholder="Search..."
                  type="text"
                  style="width: 100%"
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
                    <i class="fa-regular fa-eye"></i>
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
                    <i class="fa-regular fa-eye"></i>
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
                    <i class="fa-regular fa-eye"></i>
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
                <div style="font-size: 20px; font-weight: 700">Memo</div>
                <div>
                  <textarea rows="4" class="form-control"></textarea>
                </div>
              </div>
            </div>

            <div class="col-md-2"></div>

            <div class="col-12 col-md-5">
              <div class="row">
                <div class="col-6 mb-3 mb-md-0">
                  <div style="font-weight: 600; font-size: 20px;" class="mb-2">
                    Amount to Apply
                  </div>
                  <div style="font-weight: 600; font-size: 20px;">
                    Amount to Credit
                  </div>
                </div>
                <div class="col-6">
                  <div class="d-flex justify-content-end align-items-end flex-column">
                    <div style="font-weight: 600; font-size: 20px;" class="mb-2">
                      $ 300.00
                    </div>
                    <div style="font-weight: 600; font-size: 20px;">
                      $ 0.00
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <!-- footer end -->

          <div class="d-flex justify-content-end mt-3">
            <button class="rounded-5 py-2 px-3" style="font-size: 20px; font-weight: 600; background-color: #fff">
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
</style>
