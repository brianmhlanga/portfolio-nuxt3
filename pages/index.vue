<template>
  <NuxtLayout name="default">
    <div>
      <Header />
      <div class="bg-white">
        <div
          id="about"
          class="md:w-10/12 lg:w-10/12 xl:w-9/12 pt-16 md:py-20 lg:pt-24 mx-auto"
        >
          <TextLeftImgRight />
        </div>
      </div>
      <Skills id="skills" :skill-set="skillSet" />
      <div id="projects"></div>
      <WorkSection id="works" :working-projects="workingProjects" />
      <HobbySection :hobbies="hobbies" />
      <div class="bg-white">
        <Contact id="contact" />
      </div>
    </div>
  </NuxtLayout>
</template>
<script setup>
const jsonLd = {
  "@context": "https://schema.org/",
  "@type": "WebSite",
  name: "Po Yi Zhi, Front End Developer",
  author: {
    "@type": "Person",
    "@id": "#poyizhi",
  },
  url: "https://www.eazypau.com/",
  description:
    "Personal Portfolio Website. I'm a Front-End Web Developer based in Kuala Lumpur, Malaysia. Currently focused on developing website using Vue and React. Checkout my projects and github repositories",
  keywords:
    "Web Developer, Front End Developer, Frontend Developer, Junior Web Developer, Software Developer, Software Engineer, Po Yi Zhi, Yi Zhi, Po YZ, YZ Po, eazypau, Malaysia",
  image: "https://www.eazypau.com/profile-pics/profile.webp",
};
const personJson = {
  "@context": "https://schema.org/",
  "@type": "Person",
  "@id": "#poyizhi",
  name: "Po Yi Zhi",
  email: "poyizhi@gmail.com",
  url: "https://www.eazypau.com/",
};
useHead({
  script: [
    {
      children: JSON.stringify(jsonLd),
      type: "application/ld+json",
    },
    {
      children: JSON.stringify(personJson),
      type: "application/ld+json",
    },
  ],
});
definePageMeta({
  layout: false,
});
const skillSet = [
  "HTML",
  "CSS",
  "JavaScript",
  "Vue",
  "Nuxt",
  "TypeScript",
  "Tailwind",
  "Shopify",
  "jQuery",
  "SASS",
  "PrestaShop",
  "Bootstrap",
  "Git",
];
const hobbies = [
  {
    title: "Watching the news",
    text: "Best way to start the morning",
    classBg: "bg-tea",
  },
  {
    title: "Blog Writing",
    text: "To pen down my thoughts",
    classBg: "bg-blog",
  },
  {
    title: "Grocery Shopping",
    text: "Buy some of my favourite snacks",
    classBg: "bg-grocer",
  },
  {
    title: "Listening to music",
    text: "Recent favourites: Bastille, HONNE, Milet and Yoasobi",
    classBg: "bg-music",
  },
];
const projects = [
  {
    isReverse: false,
    title: "Oacey ERP",
    titleColor: "text-white",
    filterColor: "bg-slate-900 bg-opacity-60",
    imageUrl: "/project-ss/chatapp-ss.webp",
    description:
      "An enterprise resource planning tool for Petalm Africa Group",
    techStack: [
      "Vue",
      "TS",
      "Vite",
      "TailwindCSS",
      "Firebase",
      "Pinia",
      "Vue-router",
    ],
    isUrl: true,
    urlLink: "https://eazy-chat-app.netlify.app/login",
    githubLink: "https://github.com/eazypau/chatApp",
  },
  {
    isReverse: true,
    title: "Spotify Clone",
    titleColor: "text-white",
    filterColor: "bg-slate-500 mix-blend-hard-light",
    imageUrl: "/project-ss/spotify-ss.webp",
    description:
      "A Spotify clone web app. Built to view your saved and created playlist. It also can control your Spotify app playback state.",
    techStack: [
      "Vue",
      "Vite",
      "TailwindCSS",
      "Vuex",
      "Vue-router",
      "Spotify Web API",
    ],
    isUrl: false,
    githubLink: "https://github.com/eazypau/spotify-clone-web",
  },
  {
    isReverse: false,
    title: "Shopping Cart",
    titleColor: "text-white",
    filterColor: "bg-slate-700 bg-opacity-60",
    imageUrl: "/project-ss/shopping-cart-ss.webp",
    description:
      "A static E-Commerce website to demonstrate the flow of a user purchase",
    techStack: ["React", "SASS", "React-router"],
    isUrl: true,
    urlLink: "https://eazypau.github.io/shopping-cart-react/#/",
    githubLink: "https://github.com/eazypau/shopping-cart-react",
  },
  {
    isReverse: true,
    title: "Kanban Board",
    titleColor: "text-white",
    filterColor: "bg-slate-800 bg-opacity-60",
    imageUrl: "/project-ss/kanban-board.webp",
    description: "A Kanban board to store the user's task list.",
    techStack: [
      "React",
      "SASS",
      "TailwindCSS",
      "Local Storage",
      "React-beautiful-dnd",
    ],
    isUrl: true,
    urlLink: "https://eazypau.github.io/kanban-board-react/",
    githubLink: "https://github.com/eazypau/kanban-board-react",
  },
  {
    isReverse: false,
    title: "Saloon Booking Web",
    titleColor: "text-white",
    filterColor: "bg-slate-900 bg-opacity-60",
    imageUrl: "/project-ss/saloonbooking-ss.webp",
    description:
      "A door-to-door saloon appointment booking website allows users to book their appointment at any time.",
    techStack: [
      "Vue",
      "TS",
      "Vite",
      "TailwindCSS",
      "Firebase",
      "Vuex",
      "Vue-router",
    ],
    isUrl: true,
    urlLink: "https://saloonbooking-95d49.web.app/",
    githubLink: "https://github.com/eazypau/saloonbooking",
  },
  {
    isReverse: true,
    title: "Tic Tac Toe",
    titleColor: "text-white",
    filterColor: "bg-zinc-700 mix-blend-hard-light",
    imageUrl: "/project-ss/tictactoe-ss.webp",
    description: "A game of tic tac toe in HTML, CSS, and JavaScript.",
    techStack: ["HTML", "CSS", "JavaScript"],
    isUrl: true,
    urlLink: "https://eazypau.github.io/tictactoe/",
    githubLink: "https://github.com/eazypau/tictactoe",
  },
];
const workingProjects = [
  {
    image: {
      src: "/work/ok gxc.png",
      alt: "LVLY",
      width: "410",
      height: "117",
    },
    imageShowcase: [
      {
        src: "/work/ok gxc.png",
        alt: "LVLY product page",
        width: "726",
        height: "460",
      },
    ],
    heading: "Ok Grand Challenge",
    // description: `LVLY, Bloomeroo, and Flowerchimp are e-commerce websites for selling flower products.
    // This was created using Shopify Liquid, HTML, CSS, and Javascript. Customers can choose their desired
    // delivery date and timeslot for their order. It allows customers to select their desired flower products
    // , add-on products, and gifts for various occasions. The online stores are available mainly in Southeast
    // Asia and Australia.`,
    description: `Ok Grand Challenge is a promotion by one of Zimbabwe biggest groceries chain store which is
    hosted annually, was involved in the development of the automated raffle system for the Grand Draw`,
    urls: [
      {
        name: "LVLY AU",
        link: "#",
      },
      {
        name: "LVLY MY",
        link: "#",
      },
    ],
  },
  {
    image: {
      src: "/work/delta.png",
      alt: "Flowerchimp",
      width: "410",
      height: "205",
    },
    imageShowcase: [
      {
        src: "/work/delta1.png",
        alt: "Flowerchimp product page",
        width: "726",
        height: "460",
      },
      {
        src: "/work/delta2.png",
        alt: "Flowerchimp home page",
        width: "726",
        height: "460",
      },
      {
        src: "/work/delta1.png",
        alt: "Flowerchimp cart page",
        width: "726",
        height: "460",
      },
    ],
    heading: "Delta Beverages Online Store",
    // description: `LVLY, Bloomeroo, and Flowerchimp are e-commerce websites for selling flower products.
    // This was created using Shopify Liquid, HTML, CSS, and Javascript. Customers can choose their desired
    // delivery date and timeslot for their order. It allows customers to select their desired flower products
    // , add-on products, and gifts for various occasions. The online stores are available mainly in Southeast
    // Asia and Australia.`,
    description: `Delta Beverages Online Store is an online e-commerce platform for
    Delta Beverages Zimbabwe, I was involved in the development process as a Front-End Developer during
    my time at Contitouch Technologies`,
    urls: [
      {
        name: "Delta Beverages Online Store",
        link: "https://deltaonline.co.zw/",
      },
    ],
  },
  {
    image: {
      src: "/work/medorange.png",
      alt: "Bloomeroo",
      width: "410",
      height: "82",
    },
    imageShowcase: [
      {
        src: "/work/med1.png",
        alt: "Bloomeroo product page",
        width: "726",
        height: "460",
      },
      {
        src: "/work/med2.png",
        alt: "Bloomeroo home page",
        width: "726",
        height: "460",
      },
      {
        src: "/work/med3.png",
        alt: "Bloomeroo cart page",
        width: "726",
        height: "460",
      },
    ],
    heading: "Oacey ERP",
    // description: `LVLY, Bloomeroo, and Flowerchimp are e-commerce websites for selling flower products.
    // This was created using Shopify Liquid, HTML, CSS, and Javascript. Customers can choose their desired
    // delivery date and timeslot for their order. It allows customers to select their desired flower products
    // , add-on products, and gifts for various occasions. The online stores are available mainly in Southeast
    // Asia and Australia.`,
    description: `MedOrange is one of the leading e-commerce sites for pharmaceutical products in Zimbabwe,
    I was involved in the development process as a Front-End Developer at Contitouch Technologies a software development company in Zimbabwe`,
    urls: [
      {
        name: "MedOrange Online Store",
        link: "https://www.medorange.com/",
      },
    ],
  },
  {
    image: {
      src: "/work/oacey.png",
      alt: "The Hacker Collection Website",
      width: "62",
      height: "65",
    },
    imageShowcase: [
      {
        src: "/work/oacey1.png",
        alt: "The Hacker Collective startup page",
        width: "726",
        height: "460",
      },
      {
        src: "/work/oacey2.png",
        alt: "The Hacker Collective home page",
        width: "726",
        height: "460",
      },
      {
        src: "/work/oacey1.png",
        alt: "The Hacker Collective invest page",
        width: "726",
        height: "460",
      },
    ],
    heading: "Oacey ERP",
    // description: `A landing page website to display company information, businesses,
    // programs, etc. This was created using Vue, Nuxt3, TailwindCSS,
    // Javascript, and Headless UI.`,
    description: `Oacey ERP is an enterprise resource planning tool currently under development
    by Petalm Africa Group, it has modules ranging from loan management, leave management, timesheet management, perfomance management and Employee Management and 
    I have been involved in the project as a Full Stack software developer.`,
    urls: [
      {
        name: "Oacey",
        link: "#",
      },
    ],
  },
];
</script>
