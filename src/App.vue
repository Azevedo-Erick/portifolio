<template>
  <div id="app">
    <NavegationBar/>
    <StartPart/>
    <AboutMe/>
    <Skills/>
    <Labs/>
    <Contact/>
    <Footer/>
  </div>
</template>

<script>
import NavegationBar from './components/NavegationBar.vue';
import StartPart from './components/StartPart.vue';
import AboutMe from './components/AboutMe.vue';
import Skills from './components/Skills.vue';
import Labs from './components/Labs.vue'
import Contact from './components/Contact.vue';
import Footer from './components/footer.vue';
export default {
  name: 'Portifolio',
  components: {
    NavegationBar,
    StartPart,
    AboutMe,
    Skills,
    Labs,
    Contact,
    Footer
  }
}
</script>

<style>
@import url("https://fontlibrary.org//face/glacial-indifference");
@import url("https://fontlibrary.org//face/bebas");
@import url('https://fonts.googleapis.com/css2?family=Anonymous+Pro&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Nunito:ital@1&display=swap');

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
  overflow-x: hidden;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}

</style>
