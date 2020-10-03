<template>
  <div>
    <div class="card-body" style="display: flex">
      <div>
        <img
          class="card-img-top"
          :src="video.snippet.thumbnails.medium.url"
          alt="YouTube thumbnail"
          style="width: 10rem; padding-right: 2rem"
        />
      </div>
      <div>
        <h5 class="card-title">
          <a
            :href="'https://www.youtube.com/watch?v=' + video.id.videoId"
            class="card-link"
            target="_blank"
            style="color: #000;"
            >{{ video.snippet.title }}</a>
        </h5>
        <h6 class="card-subtitle mb-2 text-muted">
          {{ video.snippet.channelTitle }} |
          {{ video.snippet.publishedAt | formatDate }}
        </h6>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
};
</script>