<template>
	<div class="author">

		<g-image alt="Author image" class="author__image" src="https://lh3.googleusercontent.com/a-/AOh14GhQx7CJ7k7remJ3QCGILQSktZ7XCjopKrtW4e3cPYQ=s96-c-rg-br100" width="180" height="180" blur="5" />

		<h1 v-if="showTitle" class="author__site-title">
			{{ $static.metadata.siteName }}
		</h1>

		<p class="author__intro">
			Josep V. Monjo
		</p>

		<p class="author__links">
			<a href="//twitter.com/monjo" target="_blank"><img class="icon" src="../assets/images/twitter.svg" alt="twiter"></a>
			<a href="//github.com/jvmonjo" target="_blank"><img class="icon" src="../assets/images/github.svg" alt="github"></a>
		</p>

	</div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
	props: ['showTitle']
}
</script>

<style lang="scss">
.icon {
	height: 30px;
	width: 30px;
}
.author {
	margin: 0 auto;
	max-width: 500px;
	text-align: center;
	padding: calc(var(--space) / 2) 0;

	&__image {
		border-radius: 100%;
		width: 90px;
		height: 90px;
		margin-bottom: 1em;
	}

	&__intro {
		opacity: .8;
	}

	&__site-title {
		font-size: 1.5em;
	}

	&__links {
		margin-top: -.5em;
		a {
			margin: 0 .5em;
			text-decoration: none;
		}
	}
}
</style>
