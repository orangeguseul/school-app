<script>
    let Grade
    let Class
    let enter = ()=>{
        localStorage.setItem('Class', Class);
        localStorage.setItem('Grade' , Grade);
        ClassInputActive = false;
    }
    let cancel = ()=>{
        ClassInputActive = false;
    }
    export let ClassInputActive = false;
</script>
{#if ClassInputActive}
<div
class="relative z-10"
aria-labelledby="modal-title"
role="dialog"
aria-modal="true"
>
<!--
Background backdrop, show/hide based on modal state.

Entering: "ease-out duration-300"
From: "opacity-0"
To: "opacity-100"
Leaving: "ease-in duration-200"
From: "opacity-100"
To: "opacity-0"
-->
<div class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity" />

<div class="fixed inset-0 z-10 overflow-y-auto">
  <div
    class="flex min-h-full items-end justify-center p-4 text-center sm:items-center sm:p-0"
  >
    <!--
  Modal panel, show/hide based on modal state.

  Entering: "ease-out duration-300"
    From: "opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
    To: "opacity-100 translate-y-0 sm:scale-100"
  Leaving: "ease-in duration-200"
    From: "opacity-100 translate-y-0 sm:scale-100"
    To: "opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
-->
    <div
      class="relative transform overflow-hidden rounded-lg bg-white text-left shadow-xl transition-all sm:my-8 sm:w-full sm:max-w-lg"
    >
      <div class="bg-[#1a1e23] px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
        <div class="sm:flex sm:items-start">
          <div
            class="mx-auto flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-full sm:mx-0 sm:h-10 sm:w-10"
          >
            <!-- Heroicon name: outline/exclamation-triangle -->
            <img src="settings.svg" alt="logo" />
          </div>
          <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
            <h3
              class="text-lg font-medium leading-6 text-slate-300"
              id="modal-title"
            >
              반 바꾸기
            </h3>
            <div class="mt-2">
              <p class="text-white">학년</p>
              <input
                type="number"
                bind:value={Grade}
                class="caret-slate-400 border-slate-400 border-2 rounded-lg focus: outline-none"
              />
              <p class="text-white">반</p>
              <input
                type="number"
                bind:value={Class}
                class="caret-slate-400 border-slate-400 border-2 rounded-lg focus: outline-none"
              />
            </div>
          </div>
        </div>
      </div>
      <div
        class="bg-[#1a1e23] px-4 py-3 sm:flex sm:flex-row-reverse sm:px-6"
      >
        <button
          type="button"
          on:click={enter}
          class="inline-flex w-full justify-center rounded-md border border-transparent bg-red-600 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2 sm:ml-3 sm:w-auto sm:text-sm"
          >확인</button
        >
        <button
          type="button"
          on:click={cancel}
          class="mt-3 inline-flex w-full justify-center rounded-md border border-gray-400 bg-slate-700 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-slate-600 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm"
          >취소</button
        >
      </div>
    </div>
  </div>
</div>
</div>
{/if}