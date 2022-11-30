<script>
  import { spring } from "svelte/motion";
  let ios = "IOIOIOIOIOIOIOIO";
  //let ios = "IO";
  let activeIndex = 0;
  setInterval(() => {
    activeIndex = (activeIndex + 1) % ios.length;
    rotation.set(22.5 * i - activeIndex * 22.5);
  }, 1000);

  let rotation = spring(0, {
    stiffness: 0.1,
    damping: 0.25,
  });
</script>

<div
  class="text-3xl absolute m-auto inset-0 origin-center inline-flex w-20 justify-center"
  class:text-gray-700={i !== activeIndex}
  style={`rotate:${22.5 * i - activeIndex * 22.5}deg`}
>
  {io}
</div>
