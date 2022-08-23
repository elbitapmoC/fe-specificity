<script>
  import Counter from "./lib/Counter.svelte";
</script>

<main>
  <h1 id="header-id" class="header header-2 header-3">Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>

  <p class="text read-the-docs">
    Check out SvelteKit, the official Svelte app framework powered by Vite!
  </p>
</main>

<style>
  /* ------------------- TIP #1 | START
  CSS reads from top top bottom.
  The latest update to a class is the one that we will see at the end.
   */
  /* .header {
    color: red;
  }
  .header {
    color: orange;
  } */
  /* ------------------- TIP #1 | END*/

  /* ------------------- TIP #2 | START
  Specificity..
  CSS will go with header's color of pink, because (.header) is more specific.
  ID's are even MORE specific than classes.
   */
  .header {
    color: pink;
  }
  h1 {
    color: purple;
  }
  /* 
  Zero - Specificity
  --
  0 - inlinethis doesn't feel as good as the custom keybaord buyt...
  0 - id
  0 - classes
  0 - elements
   */

  /* 0,1,0,0 */
  #header-id {
    /* color: brown; */
  }
  /* -------------------TIP #2 | END*/

  /* ------------------- TIP #3 | START*/
  /* 0,0,1,0 */
  .header {
    color: pink;
  }
  /* 0,0,1,0 */
  .header-2 {
    color: red;
  }
  /* ------------------- */

  /* 0,0,1,1 */
  h1.header {
    color: pink;
  }
  /* 0,0,1,0 */
  .header-2 {
    color: red;
  }
  /* Both, same specificity, but b/c CSS is top-down. The last will take priority. */
  /* ------------------- TIP #3 | END*/

  /* ------------------- TIP #4 | START*/
  /* Important, adds another layer:
    0,0,1,0,0
    The concept still stays the same.
    If comparing two selectors, the rules from above apply.
  */
  /* 1,0,0,1,1 */
  h1.header {
    color: lavender !important;
  }
  /* 1,0,0,1,1 */
  h1.header-2 {
    color: wheat !important;
  }
  /* ------------------- TIP #4 | END*/
  /* AVOID IMPORTANT */

  .text {
    color: green;
  }
</style>
