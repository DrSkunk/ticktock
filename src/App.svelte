<script>
  let ios = "IOIOIOIOIOIOIOIO";
  let activeIndex = 0;
  let rotationIndex = 0;
  setInterval(() => {
    activeIndex = (activeIndex + 1) % ios.length;
    rotationIndex = rotationIndex + 1;
  }, 1000);
</script>

<div class="min-h-screen bg-black text-white flex justify-center items-center">
  <div class="w-96 h-96 rounded-full relative">
    <div
      class="absolute mx-auto left-0 right-0 -top-16 text-6xl inline-flex items-center"
      style="writing-mode: vertical-rl;text-orientation: upright;"
    >
      <div>T&nbsp;CK</div>
    </div>
    {#each ios as io, i}
      <div
        class="text-6xl absolute m-auto inset-0 origin-center inline-flex w-20 justify-center transition-all ease-out duration-500"
        class:text-gray-700={i !== ios.length - activeIndex}
        style={`rotate:${22.5 * i + rotationIndex * 22.5}deg`}
      >
        {io}
      </div>
    {/each}
  </div>
</div>
