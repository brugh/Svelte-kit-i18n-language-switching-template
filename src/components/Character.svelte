<script>
  import VotingButton from "./UI/Button.svelte";
  import { _, date } from "svelte-i18n";
  export let character;

  const { name, imageUrl: src, firstAppearedInFilm } = character;

  let { upVoteCount, downVoteCount } = character;
  $: totalVoteCount = upVoteCount + downVoteCount;
</script>

<div class="box">
  <div class="columns is-mobile">
    <div class="column is-one-quarter img-container">
      <img {src} alt={name} />
    </div>

    <div class="column">
      <h3 class="is-size-5 is-uppercase name">
        {name}
      </h3>

      <p class="first-appeared">
        {$_("char.appeared")}
        <span class="first-appeared-title">
          {firstAppearedInFilm.title},
        </span>
        {$date(new Date(firstAppearedInFilm.releasedAt), { format: "medium" })}
      </p>

      <div class="buttons has-addons">
        <VotingButton
          type="up"
          count={upVoteCount}
          on:click={() => (upVoteCount += 1)}
        />

        <VotingButton
          type="down"
          count={downVoteCount}
          on:click={() => (downVoteCount += 1)}
        />
        
      </div>
      <p class="is-size-7">
        {$_("char.total_votes", {values: {n: totalVoteCount}})}
      </p>

    </div>
  </div>
</div>

<style>
  .box {
    background-color: #f7f7f7;
  }
  @media screen and (min-width: 769px) {
    .box {
      height: 11rem;
    }
  }

  img {
    display: block;
    border-radius: 0.25rem;
    max-height: 100%;
    max-width: 100%;
    object-fit: cover;
  }

  .name {
    margin-top: 0;
  }

  .first-appeared {
    font-size: 0.85rem;
    margin-bottom: 0.33rem;
  }

  .first-appeared-title {
    font-style: italic;
  }

  .buttons:not(:last-child) {
    margin-bottom: unset;
  }
</style>
