<template>
	<g-link class="logo" to="/">
	  <h4 class="logo__text">{{ $static.metaData.siteName }}</h4>
	</g-link>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style lang="scss">
.logo {
	text-decoration: none;
  color: var(--body-color)!important;
	font-size: .9em;
	
	&__text {
		margin: 0;
	}
  
	&__image {
		vertical-align: middle;
		border-radius: 99px;
		height: 40px;
		width: 40px;
		margin-right: .5em;
	}	
}
</style>