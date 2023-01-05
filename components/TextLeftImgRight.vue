<template>
  <section>
    <div class="container px-6 py-8 mx-auto">
      <div class="items-center lg:flex lg:space-x-6">
        <div class="lg:w-8/12 xl:w-9/12 subFontFamily leftText">
          <h2 class="text-3xl xl:text-4xl font-bold text-gray-800">
            Who am I?
          </h2>
          <div>
            <p
              class="mt-4 text-gray-600 lg:max-w-lg xl:max-w-xl 2xl:max-w-2xl 3xl:max-w-3xl"
              style="word-spacing: 5px"
            > 
              From August 2019 when I graduated with a Bachelor of Science Honors 
              Degree in Information Technology, I have occupied roles ranging from, 
              Graphics Designing Intern, Junior Software Developer, Web Designer, 
              Web Developer upto my current role which is a Full-Stack Software Developer.

              I'm also currently developing an intrest in Data Science and Artificial Intelligence 
              which are areas i would llike to explore in the future.
            </p>
            <p
              class="mt-4 text-gray-600 lg:max-w-lg xl:max-w-xl 2xl:max-w-2xl 3xl:max-w-3xl"
              style="word-spacing: 5px"
            > 
              With about 3 to 4 years experience working with basic front-end technologies like HTML, CSS
              and CSS frameworks like bootstrap, i decided to explore more technologies like JavaScript,
              I took the FreeCodeCamp certification programmes, and took the JavaScript Algorithms and Data Structures 
              Certification, Back-End Development Certification.
              
              From that onwards, My journey in Full-Stack software development began.
            </p>
            <p
              class="mt-4 text-gray-600 lg:max-w-lg xl:max-w-xl 2xl:max-w-2xl 3xl:max-w-3xl"
              style="word-spacing: 5px"
            >
              Currently, I am working as a full-stack software developer for
              <a class="font-bold hover:underline" href="https://petalmafrica.com/"
                >Petalm Africa Holdings</a
              >.
            </p>
          </div>

          <div class="flex items-center mt-6 -mx-2">
            <a
              class="mx-2"
              href="#"
              aria-label="Instagram"
              target="blank"
            >
              <IconsInstaIcon class="IconInProfile" />
            </a>

            <a
              class="mx-2"
              href="https://www.facebook.com/brian.mhlanga.35"
              aria-label="Facebook"
              target="blank"
            >
              <IconsFacebookIcon class="IconInProfile" />
            </a>

            <a
              class="mx-2"
              href="https://www.linkedin.com/in/brian-mhlanga-009622126/"
              aria-label="Linkden"
              target="blank"
            >
              <IconsLinkedInIcon class="IconInProfile" />
            </a>

            <a
              class="mx-2"
              href="https://github.com/brianmhlanga"
              aria-label="Github"
              target="blank"
            >
              <IconsGithubIcon class="IconInProfile" />
            </a>
          </div>
        </div>

        <div class="mt-8 lg:mt-0 lg:w-4/12 xl:w-4/12">
          <div class="flex items-center justify-center lg:justify-end group">
            <div class="profileImgContainer">
              <img
                class="bg-white object-cover object-top rounded-full group-hover:grayscale transition-all ease-out duration-300"
                src="/profile-pics/brianpic.jpg"
                width="350"
                height="350"
                alt="profile image"
                loading="lazy"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script setup>
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
onMounted(() => {
  let tl = gsap.timeline({
    scrollTrigger: {
      trigger: ".leftText",
      start: "top center",
      end: "top center",
      // markers: true,
      // toggleActions: "restart pause reverse pause",
      // scrub: 1, // scrub is use set the amount of time to catch up, it kinda looks the scroll animation with ur scroller
    },
  });
  tl.addLabel("start")
    .from(".leftText", { opacity: 0, translateX: "-300px" })
    .addLabel("entering")
    .to(".leftText", { opacity: 1, translateX: "0px", duration: 1 })
    .addLabel("end");

  let imgTl = gsap.timeline({
    scrollTrigger: {
      trigger: ".profileImgContainer",
      start: "-200px center",
      end: "top center",
      // markers: true,
    },
  });
  imgTl
    .addLabel("start")
    .from(".profileImgContainer", { opacity: 0, scale: 0.5 })
    .addLabel("entering")
    .to(".profileImgContainer", { opacity: 1, scale: 1, duration: 1 })
    .addLabel("end");
});
</script>
