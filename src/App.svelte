<script>
  import Header from "./head.svelte";
  import Modal from "./Changeclass.svelte";
  let ClassInputActive = false;
  let Grade = localStorage.getItem('Grade');
  let Class = localStorage.getItem('Class');
  let ChangeClass = () =>{
  console.log('click');
  ClassInputActive = true;
  }
</script>

<main class="bg-gray-700 grid justify-center h-screen">
  <div class="bg-[#1a1e23] w-screen sm:w-96">
    <Header />
    <div class="grid justify-items-center h-5/6">
      <div class="bg-gray-700 text-center mt-10 w-4/5 rounded-3xl text-white">
        <div class="grid justify-items-center h-12">
          <div class="bg-[#1a1e23] w-1/2 rounded-b-3xl h-12">
            <h1 class="align-bottom">시간표</h1>
          </div>
          <div class="bg-[#1a1e23] w-2/3 rounded-full mt-3 h-6 select-none" on:click={ChangeClass}>{Grade}학년 {Class}반</div>
      </div>
    </div>
  </div>
  <Modal {ClassInputActive}/>
</main>
<style>
  * {
    font-family: "Noto Sans KR", sans-serif;
  }
</style>
