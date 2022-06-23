<template>
   <div>
             <div class="space-y-5 p-5 absolute bg-gray-900 ring-1 select-none w-3/4 left-16 mx-auto text-center -top-24 rounded-lg shadow-md">
                    <div class="flex justify-between items-center font-medium text-white text-lg">
                        <p>5648</p>
                        <p>3500</p>
                        <p>9208</p>
                        <p>6180</p>
                    </div>
                    <div class="flex justify-between items-baseline">
                        <p class="text-white text-2xl font-bold">$7,610.00</p>
                        <div class="space-y-1">
                            <div class="flex relative">
                                <span class="block rounded-full shadow-sm p-6 bg-gradient-to-l from-gray-50 to-transparent z-20 absolute top-0 -right-3"></span>
                                <span class="block rounded-full shadow-sm p-6 bg-gradient-to-l from-gray-50 to-transparent  mr-5"></span>
                            </div>
                            <P class="text-xs text-white font-light font-medium ml-1">master card</P> 
                        </div>
                    </div>
                </div>
                  <div class="rounded-md shadow-md bg-white pt-7 px-7 pb-0">
                       <div class="select-none">
                           <p class="text-center font-bold py-2 mt-7">Transactions</p>
                            <div class="flex items-center rounded-full bg-gray-300 justify-between py-1 px-2">
                                <p @click="handleSendForm" class="text-gray-900 duration-300 hover:text-white font-medium text-sm bg-gray-500 hover:bg-gray-800 px-20 rounded-full cursor-pointer py-2">Send</p>
                                <p @click="handleApplyForm" class="text-gray-900 duration-300 hover:text-white font-medium text-sm hover:bg-gray-800 px-20 rounded-full cursor-pointer py-2">Apply for</p>
                           </div>
                           <div v-if="showSendForm"><SendMoney /></div>
                           <div v-if="showApplyForm"><TransactionApplication /></div>
                       </div>
                  </div>
   </div>
</template>

<script>
export default {
   name : 'Landing'
}
</script>

<style>

</style>