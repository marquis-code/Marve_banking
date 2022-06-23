<template>
  <form class="bg-white p-7 rounded-md shadow-md">
    <div class="space-y-3 select-none">
      <h1 class="font-medium text-center text-xl">Withdraw Funds</h1>
      <div class="">
        <label class="text-sm font-medium text-gray-900"
          >Reciepent Account ID**</label
        >
        <input
          type="number"
          class="mt-1 bg-white rounded-md w-full bg-gray-300 p-2 shadow-sm outline-none border-none"
          placeholder="xxxx-xxxx-xxxx-xxx-xxxx-xxx"
        />
        <span class="block pt-2 text-center lg:text-sm text-xs text-gray-900 font-medium"
          >Please enter your wallet ID or destination email</span
        >
      </div>
      <div class="lg:flex justify-between items-center space-x-0 space-y-3 lg:space-x-10">
        <div>
          <label class="text-sm text-gray-900 font-medium">Amount**</label>
          <input
            type="number"
            placeholder="$300"
            class="w-full placeholder-gray-500 text-xs outline-none mt-1 border-none px-3 py-2 ring-1 ring-gray-200 rounded-md shadow-sm"
          />
        </div>
        <div>
          <label class="text-sm text-gray-900 font-medium">Reason</label>
          <input
            type="text"
            placeholder="games (optional)"
            class="w-full placeholder-gray-500 text-xs outline-none mt-1 border-none px-3 py-2 ring-1 ring-gray-200 rounded-md shadow-sm"
          />
        </div>
      </div>
      <div class="flex justify-between items-center">
        <div class="flex justify-between items-center space-x-5">
          <span class="block font-medium font-sans text-sm">Commission</span>
          <span class="block font-medium font-sans text-sm">$3</span>
        </div>
        <div class="flex justify-between items-center space-x-5">
          <span class="block font-medium font-sans text-sm">Total</span>
          <span class="block font-medium font-sans text-sm">$303</span>
        </div>
      </div>
      <div>
        <button
          class="text-white text-center w-full bg-pink-500 rounded-full p-2 font-medium"
        >
          Withdraw
        </button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "Withdraw",
};
</script>

<style></style>
