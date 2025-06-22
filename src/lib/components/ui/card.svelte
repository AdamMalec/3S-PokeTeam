<script lang="ts">
	let { name = 'Pikachu', type = 'Electric', imgSrc = '' } = $props();
</script>

<div class="card">
	<img src={imgSrc} alt="image source" />
	<h2>{name}</h2>
	<span>{type}</span>
</div>


<style>
  .card {
    position: relative;
    padding: 2rem;
    background-color: var(--card);
    border-radius: var(--radius);
    border: 2px solid var(--input);

    &:before {
      content: "";
      z-index: -1;
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      background: linear-gradient(-45deg, #caba71 0%, #c2836c 100% );
      transform: translate3d(0px, 8px, 0) scale(0.94);
      filter: blur(12px);
      opacity: var(0.7);
      transition: opacity 0.3s;
      border-radius: inherit;
    }
  }

   h2 {
    color: var(--card-foreground);
    font-size: 1.6rem;
   }
</style>
