<script>
  import Logo from "../img/logo.png";
  import { Motion } from 'svelte-motion';
  let showPanel = false;

  function togglePanel() {
    showPanel = !showPanel;
  }
  const container = {
  hidden: { opacity: 1, scale: 0},
  
  visible: {
    opacity: 1,
    scale: 1,
    transition: {
      delayChildren: 0.3,
      staggerChildren: 0.2
    }
  },

}

const item = {
 
    hidden: { y: 20, opacity: 0 },
    visible: { y: 0, opacity: 1 }
  
}
</script>

{#if showPanel}
 
  <Motion let:motion variants={container} initial="hidden" animate="visible"}> 
    <div use:motion class="fixed bg-gray-600/75 top-0 right-0 backdrop-blur-lg mt-16 z-50 p-4 min-[1100px]:hidden w-screen h-[100%]">
    <div class="flex flex-col justify-center items-center text-center space-y-[20px] text-white text-lg">
  <Motion let:motion variants={item} initial={{y: 20, opacity: 0, filter: "blur(10px)"}} animate={{y: 0, opacity: 1, filter: "blur(0px)"}}>
  <a use:motion href="/" class=" transition-colors focus:outline-none focus-visible:ring-2 focus-visible:ring-offset-2  duration-200 ease-in-out active:border-black transform active:scale-95 disabled:opacity-50 disabled:cursor-not-allowed disabled:border-gray-400 disabled:text-gray-400 hover:bg-[#363636]/50 p-[5px] rounded-md">Home</a>
  </Motion>
    <Motion let:motion variants={item} initial={{y: 20, opacity: 0, filter: "blur(10px)"}} animate={{y: 0, opacity: 1, filter: "blur(0px)"}}>
  <a use:motion href="/about" class=" transition-colors focus:outline-none focus-visible:ring-2 focus-visible:ring-offset-2  duration-200 ease-in-out active:border-black transform active:scale-95 disabled:opacity-50 disabled:cursor-not-allowed disabled:border-gray-400 disabled:text-gray-400 hover:bg-[#363636]/50 p-[5px] rounded-md px-[7px]">About</a>
  </Motion>
  <Motion let:motion variants={item} initial={{y: 20, opacity: 0, filter: "blur(10px)"}} animate={{y: 0, opacity: 1, filter: "blur(0px)"}}>
  <a use:motion href="/contacts" class=" transition-colors focus:outline-none focus-visible:ring-2 focus-visible:ring-offset-2  duration-200 ease-in-out active:border-black transform active:scale-95 disabled:opacity-50 disabled:cursor-not-allowed disabled:border-gray-400 disabled:text-gray-400 hover:bg-[#363636]/50 p-[5px] rounded-md px-[7px]">Contacts</a>
  </Motion>
  <Motion let:motion variants={item} initial={{y: 20, opacity: 0, filter: "blur(10px)"}} animate={{y: 0, opacity: 1, filter: "blur(0px)"}}>
  <a use:motion href="/career" class=" transition-colors focus:outline-none focus-visible:ring-2 focus-visible:ring-offset-2  duration-200 ease-in-out active:border-black transform active:scale-95 disabled:opacity-50 disabled:cursor-not-allowed disabled:border-gray-400 disabled:text-gray-400 hover:bg-[#363636]/50 p-[5px] rounded-md px-[7px]">Careers</a>
  </Motion>
    </div>
  </div></Motion>
{/if}

<nav class="nav-container overflow-hidden fixed h-67 grid min-[1100px]:justify-end min-[1100px]:space-x-5 text-center content-center text-[15px] font-semibold align-middle items-center text-[#000000] w-full bg-white top-0 left-0 z-10 drop-shadow-xl">
  <a class="absolute justify-start ml-[10px] " href="/">
    <div class="flex items-center flex-nowrap" >
     <img src="{Logo.src}" alt="logo" class="size-[60px] "/>
     <h1 class="font-semibold size-full text-[18px] ml-3 max-[1100px]:hidden">The Lions Textile Industries</h1>
      <h1 class="font-black text-orange-400 size-full text-[20px] max-[1100px]:hidden w-[1px]">.</h1>
    </div>
  </a>
    
  <div class="space-x-5 pr-[50px]">
  <a href="/" class="transition-[color, transform] ease-in-out duration-200 max-[1100px]:hidden hover:bg-[#EE9935]/50 p-[5px] rounded-md px-[7px]">Home</a>
  <a href="/about" class=" transition-[color, transform] ease-in-out duration-200 max-[1100px]:hidden hover:bg-[#EE9935]/50 p-[5px] rounded-md px-[7px]">About</a>
  <a href="/contacts" class=" transition-[color, transform] ease-in-out duration-200 max-[1100px]:hidden hover:bg-[#EE9935]/50 p-[5px] rounded-md px-[7px]">Contacts</a>
  <a href="/career  " class=" transition-[color, transform] ease-in-out duration-200 max-[1100px]:hidden hover:bg-[#EE9935]/50 p-[5px] rounded-md px-[7px] ">Careers</a>
  </div>
<div class="flex justify-end">
 <button on:click={togglePanel} class=" transition-[colors, transform] min-[1100px]:hidden fa-solid {showPanel ? 'fa-x' : 'fa-ellipsis-vertical'} p-[10px] rounded-md ml-[10px] float-right m-[15px] focus:outline-none focus-visible:ring-2 duration-300 focus-visible:ring-offset-2  ease-in-out transform active:scale-90 disabled:opacity-50 disabled:cursor-not-allowed disabled:border-gray-400 disabled:text-gray-400 min-[1100px]:justify-end "></button>
</div>
 
</nav>
