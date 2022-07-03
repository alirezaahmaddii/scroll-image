<template>
  <div class="container">
    <article class=" content  ">
      <div class="container">
        <section class="slow">
          <div class="d-flex cart-items text-items show-text" style="background: #ffffff" >
            <div class="d-flex flex-column">
              <p><strong>The history of pizza begins in antiquity, when various ancient cultures produced flatbreads with
                toppings.</strong></p>

              <p>The word pizza was first documented in AD 997 in Gaeta and successively in different parts of Central and
                Southern Italy. The precursor of pizza was probably the focaccia, a flat bread known to the Romans as
                panis
                focacius, to which toppings were then added.</p>

              <p>Modern pizza developed in Naples, when tomato was added to the focaccia in the late 18th century.
                However,
                pizza
                was mainly eaten in the country of Italy and by immigrants from there. This changed after World War II,
                when
                Allied troops stationed in Italy came to enjoy pizza along with other Italian foods.</p>
            </div>
          </div>
        </section>
        <section>

          <figure>
            <img src="/media/image/mobility.jpg"
                 class="inline-photo show-on-scroll">
          </figure>
        </section>
        <section class="slow">
          <div class="d-flex cart-items show-text" style="background: #ffffff" >
            <div class="d-flex flex-column">
              <h2>Make an Italian pizza</h2>

              <p>(makes dough for 4 pizzas, each one about 12 inches in diameter)</p>

              <h3>Ingredients</h3>

              <ul>
                <li>600 mL of warm water</li>
                <li>7 cups (1kg) flour</li>
                <li>2.5 – 3 tablespoons (25 grams) of fresh yeast or 2 teaspoons (7-8 grams) of dried yeast</li>
                <li>6 tablespoons of extra virgin olive oil</li>
                <li>1.5 teaspoons salt</li>
                <li>2 teaspoons sugar</li>
              </ul>
            </div>
          </div>
        </section>
        <section>
          <figure>
            <img src="/media/image/strength-score-v4.jpg" class="inline-photo show-on-scroll">
          </figure>
        </section>
        <section>

          <div class="d-flex card-items show-text" style="background: #ffffff" >
            <div class=" d-flex flex-column">
              <h3>Method</h3>

              <p>Sprinkle the yeast into a medium bowl with the warm water. We don’t mean hot, and we don’t mean cold… we
                mean
                warm! That’s the kind the yeast likes best. Stir until the yeast dissolves.</p>

              <p>Place almost all of the flour on the table in the shape of a volcano. (Think Mt. Vesuvius… appropriate
                since
                Naples is the king of all pizza cities!).</p>

              <p>Pour the yeast-and-warm-water mix, along with the other ingredients, into the “crater” of the
                volcano.</p>

              <p>Knead everything together for 10 to 15 minutes until the dough is smooth and elastic, keeping your
                surface
                floured.</p>
            </div>
          </div>
        </section>
        <section>
          <div>
            <figure>
              <img src="media/image/yoga.jpg"
                   class="inline-photo show-on-scroll">
            </figure>
          </div>
        </section>
        <section>
          <div class="d-flex card-items show-text" style="background: #ffffff" >
            <div>
              <p>Transfer the dough onto an oiled pizza pan or baking sheet.</p>

              <p>Add tomato sauce, if you want a pizza rossa (red pizza). Lots of pizzas in Italy are actually pizza
                bianca,
                without tomato sauce, so don’t feel like you have to! Brush the edges of the crust with a little bit of
                olive
                oil.</p>

              <p>Bake each pizza for about 10 minutes, then add mozzarella cheese (sliced or grated) on top, as well as
                any
                other
                ingredients.</p>

              <p>Let the pizzas bake until the crust is browned and the cheese is melted. By lifting up the pizza to peek
                underneath, you can make sure the bottom has browned, too.</p>

              <p>Remove your pizzas from the oven and, for a real Italian touch, garnish with a few basil leaves. And
                enjoy!</p>
            </div>
          </div>

        </section>
        <section>
          <figure>
            <img src="/media/image/mobility.jpg"
                 class="inline-photo show-on-scroll">
          </figure>
        </section>
      </div>
    </article>
  </div>
</template>


<script>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger.js';
import 'gsap/ScrollToPlugin';

export default {
  data: () => ({}),
  methods: {
    scr() {
      // Detect request animation frame
      let scroll = window.requestAnimationFrame ||
          // IE Fallback
          function (callback) {
            window.setTimeout(callback, 100 * 100)
          };
      let elementsToShow = document.querySelectorAll('.show-on-scroll');
      let showText = document.querySelectorAll('.show-text');

      function loop() {
        Array.prototype.forEach.call(showText, function (element) {
          if (isElementInViewport(element)) {
            element.classList.add('show-text');
          } else {
            element.classList.remove('show-text');
          }
        });

        Array.prototype.forEach.call(elementsToShow, function (element) {
          if (isElementInViewport(element)) {
            element.classList.add('is-visible');
          } else {
            element.classList.remove('is-visible');
          }
        });

        scroll(loop);
      }

// Call the loop for the first time
      loop();

// Helper function from: http://stackoverflow.com/a/7557433/274826
      function isElementInViewport(el) {
        // special bonus for those using jQuery
        if (typeof jQuery === "function" && el instanceof jQuery) {
          el = el[0];
        }
        let rect = el.getBoundingClientRect();
        return (
            (rect.top <= 0
                && rect.bottom >= 0)
            ||
            (rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &&
                rect.top <= (window.innerHeight || document.documentElement.clientHeight))
            ||
            (rect.top >= 0 &&
                rect.bottom <= (window.innerHeight || document.documentElement.clientHeight))
        );
      }
    },
  },
  mounted() {
    this.scr();
  }

}

</script>


<style lang="scss">
*, *:before, *:after {
  box-sizing: inherit;
  margin: 0;
  padding: 0;
  border: 0 none;
  position: relative;
}

article {
  .inline-photo {
    //border: 1em solid #fff;
    //border-bottom: 4em solid #fff;
    border-radius: 11px;
    box-shadow: 0em 0em 1px 3px rgb(122 122 122 / 16%);
    //margin: 2em auto;
    opacity: 0;
    transform: translateY(120px);
    transition:all .6s ease-out;
    max-width: 600px;
    width: 90%;
    will-change: transform, opacity;


  }

  .inline-photo.is-visible {
    opacity: 1;
    transition: 0.6s all ease-in-out;
    //transform: rotateZ(0deg);
    transform: translateY(20px);
  }

  header {
    opacity: 0;
    transition: opacity .6s ease-out;
  }

  header.is-visible {
    transition: 0.6s all ease-in-out;
    opacity: 1;
  }


  .main-photo {
    transform: scale(.8);
  }

  .heading {
    transform: translate(-50%, calc(-50% + 1em));
  }

  .is-visible .main-photo {
    transform: none;
  }

  .is-visible .heading {
    transform: translate(-50%, -50%);
  }

  .main-photo,
  .heading {
    transition: transform 4s .25s cubic-bezier(0, 1, .3, 1),
    filter 10s 5s ease-out;
    will-change: transform;
  }


  figure:nth-of-type(n)::after {
    right: 45%;
    left: 5vmin;
  }

   section {
    width: calc(50% + 1px);
    height: 65vh;
    margin-left: auto;
    position: sticky;
    top: 0;
    overflow: hidden;
    padding: 6vmin;
  }

  //section:nth-of-type(1) {
    //margin: 0 0 10vh 0;
    //width: 50%;
  //}
  //
  //figure:nth-of-type(2n) {
  //  margin: 0 0 10vh auto;
  //}
  //
  section:nth-of-type(2n+1) {
    margin: 0 auto 0 0;
    transform: translateY(20px);
    transition: 0.5s all ease-in-out;
  }
  //figure:last-of-type,
  //section:last-of-type {
  //  margin-bottom: 0;
  //}

  figure img {
    min-width: 100%;
    min-height: 100%;
    object-fit: cover;
    object-position: center;
  }

  section > div {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    //padding: 1rem;
  }

}
.cart-items{
  background: #ffffff;
  height: 56vh;
  border-radius: 10px;
  border: 1px solid #837d7d;
  box-shadow: 0px 3px 12px #6a6464;
  padding: 29px 53px;
  opacity: 0;
  transition: 0.5s all ease-in-out;

}
.card-items {
  background: #ffffff;
  height: 56vh;
  border-radius: 10px;
  border: 1px solid #837d7d;
  box-shadow: 0px 3px 12px #6a6464;
  padding: 29px 53px;
  opacity: 0;
  transition: 0.5s all ease-in-out;
}
.show-text{
  opacity: 1;
  transition: 0.4s all ease-in-out;

}
.slow{
  transition: 0.3s all ease-in-out;
}
</style>
