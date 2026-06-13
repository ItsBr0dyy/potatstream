<script lang="ts">
  import { browser } from "$app/environment";
  let channel = "PotatBotat";
  let host = browser ? window.location.hostname : '';
</script>

<div class="layout">
  <div class="stream">
    <iframe
      src={`https://player.twitch.tv/?channel=${channel}&parent=${host}&darkpopout`}
      height="100%"
      width="100%"
      title="stream"
      allowfullscreen
    ></iframe>
  </div>

  <div class="chat">
    <iframe
      src={`https://www.twitch.tv/embed/${channel}/chat?parent=${host}&darkpopout`}
      height="100%"
      width="100%"
      title="chat"
    ></iframe>
  </div>
</div>

<style>
  :global(html, body) {
    margin: 0;
    height: 100%;
    background: #0e0e10;
  }

  .layout {
    display: flex;
    height: 100vh;
    width: 100%;
    background: #0e0e10;
  }

  .stream {
    flex: 3;
    min-width: 0;
  }

  .chat {
    flex: 1;
    min-width: 320px;
    border-left: 1px solid #222;
  }

  iframe {
    width: 100%;
    height: 100%;
    border: 0;
  }
</style>