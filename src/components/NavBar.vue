<template>
  <header class="SiteHeader">
    <div class="SiteContainer">
      <a class="SiteBrand" href="https://nhsproviders.org">
        <img src="https://nhsproviders.org/images/nhs-providers-logo.svg" alt="NHS Providers Logo" id="logo">
      </a>
      <div class="SiteTools">
        <ul>
          <li class="SiteTools-Login profile-nav-dropdown profile-desktop">
            <div>
              <span class="Icon-User"></span>
              <a href="https://portal.nhsproviders.org/account/login" target="_blank">
                <span class="SiteTools-Text">My Account</span>
              </a>
            </div>
          </li>
          <li>
            <div class="SiteTools-Social">
              <div class="SocialLinks-Item SocialLinks-Item--Twitter">
                <a href="https://www.twitter.com/nhsproviders" target="_blank" rel="noreferrer">Twitter</a>
              </div>
              <div class="SocialLinks-Item SocialLinks-Item--LinkedIn">
                <a href="https://www.linkedin.com/company/nhsproviders" target="_blank" rel="noreferrer">LinkedIn</a>
              </div>
            </div>
          </li>
        </ul>
      </div>
      <ul class="DesktopSearch">
        <li class="SiteSearch active" id="SiteSearch">
          <form action="https://nhsproviders.org/search" class="SiteSearch-Form" id="SearchForm"
            onsubmit="document.getElementsByName('q')[0];">
            <input aria-label="search" placeholder="Search" type="search" name="keywords">
            <button class="SiteSearch-Toggle" id="SiteSearch-Toggle" aria-label="Search">
              <span class="Icon-Search"></span>
              <span class="SiteTools-Text">Search</span>
            </button>
          </form>
        </li>
      </ul>
    </div>
      <nav class="PrimaryNav">
        <div class="SiteContainer">
          <ul class="PrimaryNav-level1">
            <li class="PrimaryNav-item">
                <a href="" style="outline: 0;" @click.prevent="$emit('changePage', 'Instructions')">Instructions</a>
            </li>
            <li class="PrimaryNav-item">
                <a href="" style="outline: 0;" @click.prevent="$emit('changePage', 'Section 1')"><span>Section 1</span></a>
            </li>
            <li class="PrimaryNav-item">
                <a href="" style="outline: 0;" @click.prevent="$emit('changePage', 'Section 2')"><span>Section 2</span></a>
            </li>
            <li class="PrimaryNav-item">
                <a href="" style="outline: 0;" @click.prevent><span>Scores</span></a>
            </li>
            <li class="PrimaryNav-item PrimaryNav-item--active">
                <a href="" style="outline: 0;" @click.prevent><span>Report</span></a>
            </li>
          </ul>
        </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'NavBar',
  props: {
    page: String
  },
  emits: ['changePage'],
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
