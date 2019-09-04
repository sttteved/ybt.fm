<template>
	<div class="author">

		<g-image alt="Author image" class="author__image" src="~/assets/images/yallboys.png" width="233" height="100" blur="1" />

		<h1 v-if="showTitle" class="author__site-title">
			{{ $static.metaData.siteName }}
		</h1>

		<p class="author__intro">
			{{ $static.metaData.siteName }} is {{ $static.metaData.siteTagline.toLowerCase() }}.
		</p>

		<div class="author__links">
			<a href="//facebook.com/yallboystalkin">
				<FacebookIcon></FacebookIcon>
			</a>
			<a href="//twitter.com/yallboystalkin">
				<TwitterIcon></TwitterIcon>
			</a>
			<a href="//instagram.com/yallboystalkin">
				<InstagramIcon></InstagramIcon>
			</a>
			<a href="//open.spotify.com/show/5xzMcpzL8T5g7zGqNMoQcB?si=zEyr_F4oQs6El1av3kT8iA&fbclid=IwAR3i67W65XU4Fl8HpIduxKlhzVsPwT2XP3a6vbxKc2WYUUF-SCXfPzHRWIc" class="spotify">
				<SpotifyIcon></SpotifyIcon>
			</a>
			<a href="//podcasts.apple.com/us/podcast/yall-boys-talkin/id1452781895?mt=2" class="apple">
				<ApplePodcastsIcon></ApplePodcastsIcon>
			</a>
			<a href="//play.google.com/music/listen#/ps/Icqw2qixlfgyrebhomlxrhen7k4" class="google">
				<GooglePodcastsIcon></GooglePodcastsIcon>
			</a>
		</div>

	</div>
</template>

<static-query>
query {
  metaData {
    siteName
		siteTagline
  }
}
</static-query>

<script>
import ApplePodcastsIcon from '~/assets/icons/podcasts.svg'
import FacebookIcon from '~/assets/icons/facebook.svg'
import GooglePodcastsIcon from '~/assets/icons/googlepodcasts.svg'
import InstagramIcon from '~/assets/icons/instagram.svg'
import SpotifyIcon from '~/assets/icons/spotify.svg'
import TwitterIcon from '~/assets/icons/twitter.svg'

export default {
	props: ['showTitle'],
  components: {
		ApplePodcastsIcon,
		FacebookIcon,
		GooglePodcastsIcon,
		InstagramIcon,
		SpotifyIcon,
		TwitterIcon,
  }
}
</script>

<style lang="scss">
.author {
	margin: 0 auto;
	max-width: 400px;
	text-align: center;
	padding: calc(var(--space) / 2) 0;

	// &__image {
	// 	border-radius: 100%;
	// 	width: 90px;
	// 	height: 90px;
	// 	margin-bottom: 1em;
	// }

	&__intro {
		opacity: .8;
	}

	&__site-title {
		font-size: 1.5em;
	}

	&__links {
		// margin-top: -.5em;
		a {
			margin: 0 .5em;
		}
		svg {
			font-size: 1.5em;
			width: 1em;
			height: 1em;
			fill: currentColor;
		}
	}
}
</style>