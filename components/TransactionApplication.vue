<template>
  <form class="bg-white p-7">
    <div class="space-y-3 select-none">
      <div class="lg:flex justify-between items-center space-y-3 lg:space-y-0 lg:space-x-10">
        <div>
          <label class="text-sm text-gray-900 font-medium">Amount</label>
          <input
            type="number"
            placeholder="$300"
            class="w-full placeholder-gray-500 text-xs outline-none mt-1 border-none px-3 py-2 ring-1 ring-gray-200 rounded-md shadow-md"
          />
        </div>
        <div>
          <label class="text-sm text-gray-900 font-medium">Reason</label>
          <input
            type="text"
            placeholder="games"
            class="w-full placeholder-gray-500 text-xs outline-none mt-1 border-none px-3 py-2 ring-1 ring-gray-200 rounded-md shadow-md"
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
          Apply For Loan
        </button>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "TransactionApplication",
};
</script>

<style></style>
