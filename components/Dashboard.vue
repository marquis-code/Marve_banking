<template>
  <div class="lg:flex relative lg:static">
    <div
     v-if="show_dropdown"
      id="sidebar"
      class="px-1 h-full lg:h-screen bg-gradient-to-t from-gray-800 to-green-500 w-full lg:w-40 pt-16 lg:block z-20 lg:z-0 lg:static absolute"
    >
      <ul class="select-none">
        <li
          @click="toggleHome"
          :class="[showHome ? 'bg-green-900 text-white' : '']"
          class="font-medium text-center mb-5 py-2 cursor-pointer duration-300 w-full rounded-lg hover:ring-1 hover:ring-gray-800"
        >
          Home
        </li>
        <li
          @click="toggleWithdraw"
          :class="[showWithdraw ? 'bg-green-900 text-white' : '']"
          class="font-medium text-center mb-5 py-2 cursor-pointer duration-300 w-full rounded-lg hover:ring-1 hover:ring-gray-800"
        >
          Withdraw
        </li>
        <li
          @click="toggleDeposit"
          :class="[showDeposit ? 'bg-green-900 text-white' : '']"
          class="font-medium text-center mb-5 py-2 cursor-pointer duration-300 w-full rounded-lg hover:ring-1 hover:ring-gray-800"
        >
          Deposit
        </li>
      </ul>
    </div>
    <div
      id="main_dashboard"
      class="flex-1 pt-3 container mx-auto bg-gray-600 h-full lg:h-screen"
    >
      <div :class="[show_dropdown === true ? 'px-5' : 'px-2']" class="flex justify-between items-center lg:px-5 px-2 select-none pt-2 lg:pt-0">
        <div><p class="font-medium text-xl text-white">Marquis Abah</p></div>
        <div class="hidden lg:flex"><img src="/logo.png" alt="" class="w-10 h-10" /></div>
        <div @click="toggleDropdown" class="lg:hidden space-y-1 cursor-pointer z-20">
           <div class="bg-white w-6 py-0.5"></div>
           <div class="bg-white w-6 py-0.5"></div>
           <div class="bg-white w-6 py-0.5"></div>
        </div>
      </div>
      <div class="lg:flex justify-between px-1 lg:px-5 gap-20">
        <div
          class=" lg:w-1/2 space-y-5 select-none lg:p-5 p-1 rounded-md shadow-sm lg:bg-gradient-to-t from-gray-600 to-gray-700 order-1 mt-10"
        >
          <h1 class="font-medium text-white font-sans text-xl">
            Wallet Balance
          </h1>
          <div class="flex justify-between items-center space-x-5 lg:space-x-0">
            <div
              class="space-y-1 ring-1 rounded-lg shadow-lg px-5 py-2 bg-gray-900"
            >
              <p class="block text-xs text-white font-medium font-sans">
                Total cash balance
              </p>
              <p class="block font-sans text-white font-medium text-xs lg:text-base">$1200.00</p>
            </div>
            <div
              class="space-y-1 ring-1 rounded-lg shadow-lg px-5 py-2 bg-gray-900"
            >
              <p class="block text-xs text-white font-medium font-sans">
                Credits
              </p>
              <p class="block font-sans text-white font-medium text-xs lg:text-base">$600.00</p>
            </div>
            <div
              class="space-y-1 ring-1 rounded-lg shadow-lg px-5 py-2 bg-gray-900"
            >
              <p class="block text-xs text-white font-medium font-sans">
                Debits
              </p>
              <p class="block font-sans text-white font-medium text-xs lg:text-base">$600.00</p>
            </div>
          </div>
          <div class="space-y-6">
            <div class="flex justify-between items-center px-3 lg:px-0">
              <p class="font-medium text-white font-sans lg:text-xl text-md">
                Recent transactions
              </p>
              <p
                class="lg:text-sm text-mg font-sans font-medium font-light text-green-500 cursor-pointer"
                @click="showAllTransactions"
              >
                {{ showComputedTransactions ? "Show All" : "Show Less" }}
              </p>
            </div>

            <div v-if="showComputedTransactions" class="">
              <ul
                v-for="transaction in slicedTransactions"
                :key="transaction.id"
              >
                <li
                  class="flex hover:bg-green-500 duration-300 cursor-pointer justify-between items-center rounded-lg shadow-lg ring-1 p-3 mb-6 bg-gray-900 text-sm text-white font-sans font-medium"
                >
                  <p class="text-xs lg:text-base">{{ transaction.time }}</p>
                  <p class="text-xs lg:text-base">{{ transaction.name }}</p>
                  <p class="text-xs lg:text-base">{{ transaction.amount }}</p>
                </li>
              </ul>
            </div>

            <div v-if="showTransactions" class="overflow-y-auto h-80">
              <ul v-for="transaction in transactions" :key="transaction.id">
                <li
                  class="flex hover:bg-green-500 duration-300 cursor-pointer justify-between items-center rounded-lg shadow-lg ring-1 p-3 mb-6 bg-gray-900 text-sm text-white font-sans font-medium"
                >
                  <p>{{ transaction.time }}</p>
                  <p>{{ transaction.name }}</p>
                  <p>{{ transaction.amount }}</p>
                </li>
              </ul>
            </div>
          </div>
        </div>

        <div class="lg:w-1/2 relative lg:mt-28">
          <div v-if="showHome">
            <div
              class="hidden space-y-5 w-full p-5 absolute bg-gray-900 ring-1 select-none lg:w-3/4 lg:left-16 mx-auto text-center -top-24 rounded-lg shadow-md"
            >
              <div
                class="flex justify-between items-center font-medium text-white text-lg"
              >
                <p>5648</p>
                <p>3500</p>
                <p>9208</p>
                <p>6180</p>
              </div>
              <div class="flex justify-between items-baseline">
                <p class="text-white text-2xl font-bold">$7,610.00</p>
                <div class="space-y-1">
                  <div class="flex relative">
                    <span
                      class="block rounded-full shadow-sm p-6 bg-gradient-to-l from-gray-50 to-transparent z-20 absolute top-0 -right-3"
                    ></span>
                    <span
                      class="block rounded-full shadow-sm p-6 bg-gradient-to-l from-gray-50 to-transparent mr-5"
                    ></span>
                  </div>
                  <P class="text-xs text-white font-light font-medium ml-1"
                    >master card</P
                  >
                </div>
              </div>
            </div>
            <div class="rounded-md shadow-md bg-white lg:pt-7 lg:px-7 pb-0 lg:mt-20 mt-6">
              <div class="select-none">
                <p class="text-center font-bold py-3 lg:mt-7">Transactions</p>
                <div
                  class="lg:flex items-center rounded-md mx-1 lg:mx-0 lg:rounded-full bg-gray-300 justify-between lg:py-1 py-3 px-2 mb-0"
                >
                  <p
                    @click="handleSendForm"
                    :class="[showSendForm ? 'bg-gray-800 text-white' : '']"
                    class="duration-300 text-center lg:text-justify font-medium text-sm px-20 rounded-full cursor-pointer py-2"
                  >
                    Send
                  </p>
                  <p
                    @click="handleApplyForm"
                    :class="[showApplyForm ? 'bg-gray-800 text-white' : '']"
                    class="duration-300 text-center lg:text-justify font-medium text-sm px-20 rounded-full cursor-pointer py-2"
                  >
                    Apply for
                  </p>
                </div>
                <div class="" v-if="showSendForm"><SendMoney /></div>
                <div v-if="showApplyForm"><TransactionApplication /></div>
              </div>
            </div>
          </div>
          <div v-if="showWithdraw"><Withdraw /></div>
          <div v-if="showDeposit"><Deposit /></div>
        </div>
      </div>
    </div>
    <div class="p-3 bg-black text-white text-center font-sans text-sm lg:text-base">@ marvellous_banking_2022</div>
  </div>
</template>

<script>
import SendMoney from "./SendMoney.vue";
export default {
  name: "Dashboard",
  data() {
    return {
      show_dropdown : false,
      showProfile_photo : true,
      isActive: true,
      showSendForm: true,
      showApplyForm: false,
      showTransactions: false,
      showComputedTransactions: true,
      showHome: true,
      showWithdraw: false,
      showDeposit: false,
      sidebarItems: [
        { text: "Home", link: "/#" },
        { text: "Deposit", link: "/#" },
        { text: "Withdraw", link: "/#" },
      ],
      transactions: [
        {
          id: 1,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 2,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 3,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 4,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 5,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 5,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 5,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 5,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 5,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
        {
          id: 5,
          time: "12:40PM",
          name: "spotify monthly plan",
          amount: "-$30.00",
        },
      ],
    };
  },
  computed: {
    slicedTransactions() {
      let newTransactions = this.transactions.slice(0, 3);
      return newTransactions;
    },
  },
  components: { SendMoney },
  methods: {
    handleSendForm() {
      this.showApplyForm = false;
      this.showSendForm = true;
    },
    handleApplyForm() {
      this.showSendForm = false;
      this.showApplyForm = true;
    },
    showAllTransactions() {
      this.showTransactions = !this.showTransactions;
      this.showComputedTransactions = !this.showComputedTransactions;
    },
    toggleHome() {
      this.showWithdraw = false;
      this.showHome = true;
      this.showDeposit = false;
      this.toggleDropdown()
    },
    toggleWithdraw() {
      this.showWithdraw = true;
      this.showHome = false;
      this.showDeposit = false;
      this.toggleDropdown()
    },
    toggleDeposit() {
      this.showWithdraw = false;
      this.showHome = false;
      this.showDeposit = true;
      this.toggleDropdown()
    },
    toggleDropdown(){
      this.show_dropdown = !this.show_dropdown
    }
  },
};
</script>
