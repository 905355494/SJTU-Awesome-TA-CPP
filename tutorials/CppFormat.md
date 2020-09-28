




<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
  <link rel="dns-prefetch" href="https://github.githubassets.com">
  <link rel="dns-prefetch" href="https://avatars0.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars1.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars2.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars3.githubusercontent.com">
  <link rel="dns-prefetch" href="https://github-cloud.s3.amazonaws.com">
  <link rel="dns-prefetch" href="https://user-images.githubusercontent.com/">



  <link crossorigin="anonymous" media="all" integrity="sha512-xNOnN+2GpZhQXkj5yBrbdwE//RNeJisU3rS/dibnFLGhzI+M0MeGiyt2N1cESfcID9EjasuxUgtU4fpzN1WA+g==" rel="stylesheet" href="https://github.githubassets.com/assets/frameworks-c4d3a737ed86a598505e48f9c81adb77.css" />
  
    <link crossorigin="anonymous" media="all" integrity="sha512-zUtB2ZWo+zbRCzKWWahQaHp94ByXJWAKDCen4rI/sJCaMAz+uh3G1+K23t4BzajZ7ZYFW6uUgDjDRnT5budaxw==" rel="stylesheet" href="https://github.githubassets.com/assets/github-cd4b41d995a8fb36d10b329659a85068.css" />
    
    
    
    


  <meta name="viewport" content="width=device-width">
  
  <title>TACpp/CppFormat.md at master · OneForward/TACpp</title>
    <meta name="description" content="Contribute to OneForward/TACpp development by creating an account on GitHub.">
    <link rel="search" type="application/opensearchdescription+xml" href="/opensearch.xml" title="GitHub">
  <link rel="fluid-icon" href="https://github.com/fluidicon.png" title="GitHub">
  <meta property="fb:app_id" content="1401488693436528">
  <meta name="apple-itunes-app" content="app-id=1477376905">

    <meta name="twitter:image:src" content="https://avatars0.githubusercontent.com/u/16881692?s=400&amp;v=4" /><meta name="twitter:site" content="@github" /><meta name="twitter:card" content="summary" /><meta name="twitter:title" content="OneForward/TACpp" /><meta name="twitter:description" content="Contribute to OneForward/TACpp development by creating an account on GitHub." />
    <meta property="og:image" content="https://avatars0.githubusercontent.com/u/16881692?s=400&amp;v=4" /><meta property="og:site_name" content="GitHub" /><meta property="og:type" content="object" /><meta property="og:title" content="OneForward/TACpp" /><meta property="og:url" content="https://github.com/OneForward/TACpp" /><meta property="og:description" content="Contribute to OneForward/TACpp development by creating an account on GitHub." />



  

  <link rel="assets" href="https://github.githubassets.com/">
    <link rel="shared-web-socket" href="wss://alive.github.com/_sockets/u/59958814/ws?session=eyJ2IjoiVjMiLCJ1Ijo1OTk1ODgxNCwicyI6NTg3ODA3ODcxLCJjIjoxOTI5NDE0MzM5LCJ0IjoxNjAxMjczNDcxfQ==--02884fa10eb875ebe094c63fe2c0142a4c108432f09aee3ead3627d963ceb9a8" data-refresh-url="/_alive">
  <link rel="sudo-modal" href="/sessions/sudo_modal">

  <meta name="request-id" content="656F:4D3A:1A7FF3:26063C:5F717E7F" data-pjax-transient="true" /><meta name="html-safe-nonce" content="b58f6ecda727bb9d7d6b146b869153928257c8be" data-pjax-transient="true" /><meta name="visitor-payload" content="eyJyZWZlcnJlciI6Imh0dHBzOi8vZ2l0aHViLmNvbS9PbmVGb3J3YXJkL1RBQ3BwL3RyZWUvbWFzdGVyL3R1dG9yaWFscyIsInJlcXVlc3RfaWQiOiI2NTZGOjREM0E6MUE3RkYzOjI2MDYzQzo1RjcxN0U3RiIsInZpc2l0b3JfaWQiOiI1OTY5Njg1ODk5Mzk5MjU5NTg2IiwicmVnaW9uX2VkZ2UiOiJhcC1ub3J0aGVhc3QtMSIsInJlZ2lvbl9yZW5kZXIiOiJpYWQifQ==" data-pjax-transient="true" /><meta name="visitor-hmac" content="aae8f60956b11e4910f435a6c267545359d87b6c5a0f4ab4a8e2de896e95c3d8" data-pjax-transient="true" /><meta name="cookie-consent-required" content="false" />

    <meta name="hovercard-subject-tag" content="repository:294645801" data-pjax-transient>


  <meta name="github-keyboard-shortcuts" content="repository,source-code" data-pjax-transient="true" />

  

  <meta name="selected-link" value="repo_source" data-pjax-transient>

    <meta name="google-site-verification" content="c1kuD-K2HIVF635lypcsWPoD4kilo5-jA_wBFyT4uMY">
  <meta name="google-site-verification" content="KT5gs8h0wvaagLKAVWq8bbeNwnZZK1r1XQysX3xurLU">
  <meta name="google-site-verification" content="ZzhVyEFwb7w3e0-uOTltm8Jsck2F5StVihD0exw2fsA">
  <meta name="google-site-verification" content="GXs5KoUUkNCoaAZn7wPN-t01Pywp9M3sEjnt_3_ZWPc">

  <meta name="octolytics-host" content="collector.githubapp.com" /><meta name="octolytics-app-id" content="github" /><meta name="octolytics-event-url" content="https://collector.githubapp.com/github-external/browser_event" /><meta name="octolytics-dimension-ga_id" content="" class="js-octo-ga-id" /><meta name="octolytics-actor-id" content="59958814" /><meta name="octolytics-actor-login" content="905355494" /><meta name="octolytics-actor-hash" content="20a3cb00f766f1c0555363093613205d5ad26268a8464c6d51fb2e9d0a713993" />

  <meta name="analytics-location" content="/&lt;user-name&gt;/&lt;repo-name&gt;/blob/show" data-pjax-transient="true" />

  





    <meta name="google-analytics" content="UA-3769691-2">

  <meta class="js-ga-set" name="userId" content="5706e8c4a48e5c80cfa2b7fed9f1488b">

<meta class="js-ga-set" name="dimension10" content="Responsive" data-pjax-transient>

<meta class="js-ga-set" name="dimension1" content="Logged In">



  

      <meta name="hostname" content="github.com">
    <meta name="user-login" content="905355494">


      <meta name="expected-hostname" content="github.com">

      <meta name="js-proxy-site-detection-payload" content="MWJkZTJlNzY3ZDA2MjI1YTE5Yjc5ZWNkNDc0ZmQxZmU3MjU0OGY2YjgxYTE4MzBhZmM1MjM0NWQ1OGQzYzczNHx7InJlbW90ZV9hZGRyZXNzIjoiMjAzLjEzNy4xOTUuMzkiLCJyZXF1ZXN0X2lkIjoiNjU2Rjo0RDNBOjFBN0ZGMzoyNjA2M0M6NUY3MTdFN0YiLCJ0aW1lc3RhbXAiOjE2MDEyNzM0NzEsImhvc3QiOiJnaXRodWIuY29tIn0=">

    <meta name="enabled-features" content="MARKETPLACE_PENDING_INSTALLATIONS,JS_HTTP_CACHE_HEADERS,PRESERVE_STALE_COMMENTS">

  <meta http-equiv="x-pjax-version" content="459bc655dc92a7098f9f6369c8c2d4a809a2268536ba1cb5d7dcc2ffb97257ef">
  

        <link href="https://github.com/OneForward/TACpp/commits/master.atom" rel="alternate" title="Recent Commits to TACpp:master" type="application/atom+xml">

  <meta name="go-import" content="github.com/OneForward/TACpp git https://github.com/OneForward/TACpp.git">

  <meta name="octolytics-dimension-user_id" content="16881692" /><meta name="octolytics-dimension-user_login" content="OneForward" /><meta name="octolytics-dimension-repository_id" content="294645801" /><meta name="octolytics-dimension-repository_nwo" content="OneForward/TACpp" /><meta name="octolytics-dimension-repository_public" content="true" /><meta name="octolytics-dimension-repository_is_fork" content="false" /><meta name="octolytics-dimension-repository_network_root_id" content="294645801" /><meta name="octolytics-dimension-repository_network_root_nwo" content="OneForward/TACpp" /><meta name="octolytics-dimension-repository_explore_github_marketplace_ci_cta_shown" content="false" />


    <link rel="canonical" href="https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md" data-pjax-transient>


  <meta name="browser-stats-url" content="https://api.github.com/_private/browser/stats">

  <meta name="browser-errors-url" content="https://api.github.com/_private/browser/errors">

  <link rel="mask-icon" href="https://github.githubassets.com/pinned-octocat.svg" color="#000000">
  <link rel="alternate icon" class="js-site-favicon" type="image/png" href="https://github.githubassets.com/favicons/favicon.png">
  <link rel="icon" class="js-site-favicon" type="image/svg+xml" href="https://github.githubassets.com/favicons/favicon.svg">

<meta name="theme-color" content="#1e2327">


  <link rel="manifest" href="/manifest.json" crossOrigin="use-credentials">

  </head>

  <body class="logged-in env-production page-responsive page-blob">
    

    <div class="position-relative js-header-wrapper ">
      <a href="#start-of-content" class="p-3 bg-blue text-white show-on-focus js-skip-to-content">Skip to content</a>
      <span class="progress-pjax-loader width-full js-pjax-loader-bar Progress position-fixed">
    <span style="background-color: #79b8ff;width: 0%;" class="Progress-item progress-pjax-loader-bar "></span>
</span>      
      



          <header class="Header js-details-container Details px-3 px-md-4 px-lg-5 flex-wrap flex-md-nowrap" role="banner">
    <div class="Header-item mt-n1 mb-n1  d-none d-md-flex">
      <a class="Header-link" href="https://github.com/" data-hotkey="g d"
  aria-label="Homepage " data-ga-click="Header, go to dashboard, icon:logo">
  <svg class="octicon octicon-mark-github v-align-middle" height="32" viewBox="0 0 16 16" version="1.1" width="32" aria-hidden="true"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path></svg>
</a>

    </div>

    <div class="Header-item d-md-none">
      <button class="Header-link btn-link js-details-target" type="button" aria-label="Toggle navigation" aria-expanded="false">
        <svg height="24" class="octicon octicon-three-bars" viewBox="0 0 16 16" version="1.1" width="24" aria-hidden="true"><path fill-rule="evenodd" d="M1 2.75A.75.75 0 011.75 2h12.5a.75.75 0 110 1.5H1.75A.75.75 0 011 2.75zm0 5A.75.75 0 011.75 7h12.5a.75.75 0 110 1.5H1.75A.75.75 0 011 7.75zM1.75 12a.75.75 0 100 1.5h12.5a.75.75 0 100-1.5H1.75z"></path></svg>
      </button>
    </div>

    <div class="Header-item Header-item--full flex-column flex-md-row width-full flex-order-2 flex-md-order-none mr-0 mr-md-3 mt-3 mt-md-0 Details-content--hidden-not-important d-md-flex">
          <div class="header-search header-search-current js-header-search-current flex-auto js-site-search position-relative flex-self-stretch flex-md-self-auto mb-3 mb-md-0 mr-0 mr-md-3 scoped-search site-scoped-search js-jump-to js-header-search-current-jump-to"
  role="combobox"
  aria-owns="jump-to-results"
  aria-label="Search or jump to"
  aria-haspopup="listbox"
  aria-expanded="false"
>
  <div class="position-relative">
    <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="js-site-search-form" role="search" aria-label="Site" data-scope-type="Repository" data-scope-id="294645801" data-scoped-search-url="/OneForward/TACpp/search" data-unscoped-search-url="/search" action="/OneForward/TACpp/search" accept-charset="UTF-8" method="get">
      <label class="form-control input-sm header-search-wrapper p-0 js-chromeless-input-container header-search-wrapper-jump-to position-relative d-flex flex-justify-between flex-items-center">
        <input type="text"
          class="form-control input-sm header-search-input jump-to-field js-jump-to-field js-site-search-focus js-site-search-field is-clearable"
          data-hotkey="s,/"
          name="q"
          value=""
          placeholder="Search or jump to…"
          data-unscoped-placeholder="Search or jump to…"
          data-scoped-placeholder="Search or jump to…"
          autocapitalize="off"
          aria-autocomplete="list"
          aria-controls="jump-to-results"
          aria-label="Search or jump to…"
          data-jump-to-suggestions-path="/_graphql/GetSuggestedNavigationDestinations"
          spellcheck="false"
          autocomplete="off"
          >
          <input type="hidden" value="uRSvIqnaDQZXHTcXsCD2XAdSvJ9IduAAcnQ+iTRH9tJmRIAwteV3NJ8ooTu0zsjUi9TwNGmdhO/L6eBCSmyyyQ==" data-csrf="true" class="js-data-jump-to-suggestions-path-csrf" />
          <input type="hidden" class="js-site-search-type-field" name="type" >
            <img src="https://github.githubassets.com/images/search-key-slash.svg" alt="" class="mr-2 header-search-key-slash">

            <div class="Box position-absolute overflow-hidden d-none jump-to-suggestions js-jump-to-suggestions-container">
              
<ul class="d-none js-jump-to-suggestions-template-container">
  

<li class="d-flex flex-justify-start flex-items-center p-0 f5 navigation-item js-navigation-item js-jump-to-suggestion" role="option">
  <a tabindex="-1" class="no-underline d-flex flex-auto flex-items-center jump-to-suggestions-path js-jump-to-suggestion-path js-navigation-open p-2" href="">
    <div class="jump-to-octicon js-jump-to-octicon flex-shrink-0 mr-2 text-center d-none">
      <svg height="16" width="16" class="octicon octicon-repo flex-shrink-0 js-jump-to-octicon-repo d-none" title="Repository" aria-label="Repository" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"></path></svg>
      <svg height="16" width="16" class="octicon octicon-project flex-shrink-0 js-jump-to-octicon-project d-none" title="Project" aria-label="Project" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M1.75 0A1.75 1.75 0 000 1.75v12.5C0 15.216.784 16 1.75 16h12.5A1.75 1.75 0 0016 14.25V1.75A1.75 1.75 0 0014.25 0H1.75zM1.5 1.75a.25.25 0 01.25-.25h12.5a.25.25 0 01.25.25v12.5a.25.25 0 01-.25.25H1.75a.25.25 0 01-.25-.25V1.75zM11.75 3a.75.75 0 00-.75.75v7.5a.75.75 0 001.5 0v-7.5a.75.75 0 00-.75-.75zm-8.25.75a.75.75 0 011.5 0v5.5a.75.75 0 01-1.5 0v-5.5zM8 3a.75.75 0 00-.75.75v3.5a.75.75 0 001.5 0v-3.5A.75.75 0 008 3z"></path></svg>
      <svg height="16" width="16" class="octicon octicon-search flex-shrink-0 js-jump-to-octicon-search d-none" title="Search" aria-label="Search" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M11.5 7a4.499 4.499 0 11-8.998 0A4.499 4.499 0 0111.5 7zm-.82 4.74a6 6 0 111.06-1.06l3.04 3.04a.75.75 0 11-1.06 1.06l-3.04-3.04z"></path></svg>
    </div>

    <img class="avatar mr-2 flex-shrink-0 js-jump-to-suggestion-avatar d-none" alt="" aria-label="Team" src="" width="28" height="28">

    <div class="jump-to-suggestion-name js-jump-to-suggestion-name flex-auto overflow-hidden text-left no-wrap css-truncate css-truncate-target">
    </div>

    <div class="border rounded-1 flex-shrink-0 bg-gray px-1 text-gray-light ml-1 f6 d-none js-jump-to-badge-search">
      <span class="js-jump-to-badge-search-text-default d-none" aria-label="in this repository">
        In this repository
      </span>
      <span class="js-jump-to-badge-search-text-global d-none" aria-label="in all of GitHub">
        All GitHub
      </span>
      <span aria-hidden="true" class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>

    <div aria-hidden="true" class="border rounded-1 flex-shrink-0 bg-gray px-1 text-gray-light ml-1 f6 d-none d-on-nav-focus js-jump-to-badge-jump">
      Jump to
      <span class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>
  </a>
</li>

</ul>

<ul class="d-none js-jump-to-no-results-template-container">
  <li class="d-flex flex-justify-center flex-items-center f5 d-none js-jump-to-suggestion p-2">
    <span class="text-gray">No suggested jump to results</span>
  </li>
</ul>

<ul id="jump-to-results" role="listbox" class="p-0 m-0 js-navigation-container jump-to-suggestions-results-container js-jump-to-suggestions-results-container">
  

<li class="d-flex flex-justify-start flex-items-center p-0 f5 navigation-item js-navigation-item js-jump-to-scoped-search d-none" role="option">
  <a tabindex="-1" class="no-underline d-flex flex-auto flex-items-center jump-to-suggestions-path js-jump-to-suggestion-path js-navigation-open p-2" href="">
    <div class="jump-to-octicon js-jump-to-octicon flex-shrink-0 mr-2 text-center d-none">
      <svg height="16" width="16" class="octicon octicon-repo flex-shrink-0 js-jump-to-octicon-repo d-none" title="Repository" aria-label="Repository" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"></path></svg>
      <svg height="16" width="16" class="octicon octicon-project flex-shrink-0 js-jump-to-octicon-project d-none" title="Project" aria-label="Project" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M1.75 0A1.75 1.75 0 000 1.75v12.5C0 15.216.784 16 1.75 16h12.5A1.75 1.75 0 0016 14.25V1.75A1.75 1.75 0 0014.25 0H1.75zM1.5 1.75a.25.25 0 01.25-.25h12.5a.25.25 0 01.25.25v12.5a.25.25 0 01-.25.25H1.75a.25.25 0 01-.25-.25V1.75zM11.75 3a.75.75 0 00-.75.75v7.5a.75.75 0 001.5 0v-7.5a.75.75 0 00-.75-.75zm-8.25.75a.75.75 0 011.5 0v5.5a.75.75 0 01-1.5 0v-5.5zM8 3a.75.75 0 00-.75.75v3.5a.75.75 0 001.5 0v-3.5A.75.75 0 008 3z"></path></svg>
      <svg height="16" width="16" class="octicon octicon-search flex-shrink-0 js-jump-to-octicon-search d-none" title="Search" aria-label="Search" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M11.5 7a4.499 4.499 0 11-8.998 0A4.499 4.499 0 0111.5 7zm-.82 4.74a6 6 0 111.06-1.06l3.04 3.04a.75.75 0 11-1.06 1.06l-3.04-3.04z"></path></svg>
    </div>

    <img class="avatar mr-2 flex-shrink-0 js-jump-to-suggestion-avatar d-none" alt="" aria-label="Team" src="" width="28" height="28">

    <div class="jump-to-suggestion-name js-jump-to-suggestion-name flex-auto overflow-hidden text-left no-wrap css-truncate css-truncate-target">
    </div>

    <div class="border rounded-1 flex-shrink-0 bg-gray px-1 text-gray-light ml-1 f6 d-none js-jump-to-badge-search">
      <span class="js-jump-to-badge-search-text-default d-none" aria-label="in this repository">
        In this repository
      </span>
      <span class="js-jump-to-badge-search-text-global d-none" aria-label="in all of GitHub">
        All GitHub
      </span>
      <span aria-hidden="true" class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>

    <div aria-hidden="true" class="border rounded-1 flex-shrink-0 bg-gray px-1 text-gray-light ml-1 f6 d-none d-on-nav-focus js-jump-to-badge-jump">
      Jump to
      <span class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>
  </a>
</li>

  

<li class="d-flex flex-justify-start flex-items-center p-0 f5 navigation-item js-navigation-item js-jump-to-global-search d-none" role="option">
  <a tabindex="-1" class="no-underline d-flex flex-auto flex-items-center jump-to-suggestions-path js-jump-to-suggestion-path js-navigation-open p-2" href="">
    <div class="jump-to-octicon js-jump-to-octicon flex-shrink-0 mr-2 text-center d-none">
      <svg height="16" width="16" class="octicon octicon-repo flex-shrink-0 js-jump-to-octicon-repo d-none" title="Repository" aria-label="Repository" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"></path></svg>
      <svg height="16" width="16" class="octicon octicon-project flex-shrink-0 js-jump-to-octicon-project d-none" title="Project" aria-label="Project" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M1.75 0A1.75 1.75 0 000 1.75v12.5C0 15.216.784 16 1.75 16h12.5A1.75 1.75 0 0016 14.25V1.75A1.75 1.75 0 0014.25 0H1.75zM1.5 1.75a.25.25 0 01.25-.25h12.5a.25.25 0 01.25.25v12.5a.25.25 0 01-.25.25H1.75a.25.25 0 01-.25-.25V1.75zM11.75 3a.75.75 0 00-.75.75v7.5a.75.75 0 001.5 0v-7.5a.75.75 0 00-.75-.75zm-8.25.75a.75.75 0 011.5 0v5.5a.75.75 0 01-1.5 0v-5.5zM8 3a.75.75 0 00-.75.75v3.5a.75.75 0 001.5 0v-3.5A.75.75 0 008 3z"></path></svg>
      <svg height="16" width="16" class="octicon octicon-search flex-shrink-0 js-jump-to-octicon-search d-none" title="Search" aria-label="Search" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M11.5 7a4.499 4.499 0 11-8.998 0A4.499 4.499 0 0111.5 7zm-.82 4.74a6 6 0 111.06-1.06l3.04 3.04a.75.75 0 11-1.06 1.06l-3.04-3.04z"></path></svg>
    </div>

    <img class="avatar mr-2 flex-shrink-0 js-jump-to-suggestion-avatar d-none" alt="" aria-label="Team" src="" width="28" height="28">

    <div class="jump-to-suggestion-name js-jump-to-suggestion-name flex-auto overflow-hidden text-left no-wrap css-truncate css-truncate-target">
    </div>

    <div class="border rounded-1 flex-shrink-0 bg-gray px-1 text-gray-light ml-1 f6 d-none js-jump-to-badge-search">
      <span class="js-jump-to-badge-search-text-default d-none" aria-label="in this repository">
        In this repository
      </span>
      <span class="js-jump-to-badge-search-text-global d-none" aria-label="in all of GitHub">
        All GitHub
      </span>
      <span aria-hidden="true" class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>

    <div aria-hidden="true" class="border rounded-1 flex-shrink-0 bg-gray px-1 text-gray-light ml-1 f6 d-none d-on-nav-focus js-jump-to-badge-jump">
      Jump to
      <span class="d-inline-block ml-1 v-align-middle">↵</span>
    </div>
  </a>
</li>


    <li class="d-flex flex-justify-center flex-items-center p-0 f5 js-jump-to-suggestion">
      <img src="https://github.githubassets.com/images/spinners/octocat-spinner-128.gif" alt="Octocat Spinner Icon" class="m-2" width="28">
    </li>
</ul>

            </div>
      </label>
</form>  </div>
</div>


      <nav class="d-flex flex-column flex-md-row flex-self-stretch flex-md-self-auto" aria-label="Global">
    <a class="Header-link py-md-3 d-block d-md-none py-2 border-top border-md-top-0 border-white-fade-15" data-ga-click="Header, click, Nav menu - item:dashboard:user" aria-label="Dashboard" href="/dashboard">
      Dashboard
</a>
    <a class="js-selected-navigation-item Header-link mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade-15" data-hotkey="g p" data-ga-click="Header, click, Nav menu - item:pulls context:user" aria-label="Pull requests you created" data-selected-links="/pulls /pulls/assigned /pulls/mentioned /pulls" href="/pulls">
        Pull<span class="d-inline d-md-none d-lg-inline"> request</span>s
</a>
    <a class="js-selected-navigation-item Header-link mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade-15" data-hotkey="g i" data-ga-click="Header, click, Nav menu - item:issues context:user" aria-label="Issues you created" data-selected-links="/issues /issues/assigned /issues/mentioned /issues" href="/issues">
      Issues
</a>

    <div class="d-flex position-relative">
      <a class="js-selected-navigation-item Header-link flex-auto mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade-15" data-ga-click="Header, click, Nav menu - item:marketplace context:user" data-octo-click="marketplace_click" data-octo-dimensions="location:nav_bar" data-selected-links=" /marketplace" href="/marketplace">
        Marketplace
</a>      

    </div>

  <a class="js-selected-navigation-item Header-link mt-md-n3 mb-md-n3 py-2 py-md-3 mr-0 mr-md-3 border-top border-md-top-0 border-white-fade-15" data-ga-click="Header, click, Nav menu - item:explore" data-selected-links="/explore /trending /trending/developers /integrations /integrations/feature/code /integrations/feature/collaborate /integrations/feature/ship showcases showcases_search showcases_landing /explore" href="/explore">
    Explore
</a>



    <a class="Header-link d-block d-md-none mr-0 mr-md-3 py-2 py-md-3 border-top border-md-top-0 border-white-fade-15" href="/905355494">
      <img class="avatar avatar-user" src="https://avatars0.githubusercontent.com/u/59958814?s=40&amp;v=4" width="20" height="20" alt="@905355494" />
      905355494
</a>
    <!-- '"` --><!-- </textarea></xmp> --></option></form><form action="/logout" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="4Vr2CbM6eFESTHLQUOh7DxVJXgVEBPgUrabcUPOw0+oe9MiwStkezcN2jr9yeX6hzwcpL+d+gD0JYkYlotY5TA==" />
      <button type="submit" class="Header-link mr-0 mr-md-3 py-2 py-md-3 border-top border-md-top-0 border-white-fade-15 d-md-none btn-link d-block width-full text-left" data-ga-click="Header, sign out, icon:logout" style="padding-left: 2px;">
        <svg class="octicon octicon-sign-out v-align-middle" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M2 2.75C2 1.784 2.784 1 3.75 1h2.5a.75.75 0 010 1.5h-2.5a.25.25 0 00-.25.25v10.5c0 .138.112.25.25.25h2.5a.75.75 0 010 1.5h-2.5A1.75 1.75 0 012 13.25V2.75zm10.44 4.5H6.75a.75.75 0 000 1.5h5.69l-1.97 1.97a.75.75 0 101.06 1.06l3.25-3.25a.75.75 0 000-1.06l-3.25-3.25a.75.75 0 10-1.06 1.06l1.97 1.97z"></path></svg>
        Sign out
      </button>
</form></nav>

    </div>

    <div class="Header-item Header-item--full flex-justify-center d-md-none position-relative">
      <a class="Header-link" href="https://github.com/" data-hotkey="g d"
  aria-label="Homepage " data-ga-click="Header, go to dashboard, icon:logo">
  <svg class="octicon octicon-mark-github v-align-middle" height="32" viewBox="0 0 16 16" version="1.1" width="32" aria-hidden="true"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path></svg>
</a>

    </div>

    <div class="Header-item mr-0 mr-md-3 flex-order-1 flex-md-order-none">
      

    <notification-indicator class="js-socket-channel" data-channel="eyJjIjoibm90aWZpY2F0aW9uLWNoYW5nZWQ6NTk5NTg4MTQiLCJ0IjoxNjAxMjczNDcxfQ==--2c69ef4cf979907cbad85b623599b2f502107df97302fb52f8560dd5c66c1efb">
      <a href="/notifications"
         class="Header-link notification-indicator position-relative tooltipped tooltipped-sw"
         
         aria-label="You have no unread notifications"
         data-hotkey="g n"
         data-ga-click="Header, go to notifications, icon:read"
         data-target="notification-indicator.link">
         <span class="mail-status " data-target="notification-indicator.modifier" ></span>
         <svg class="octicon octicon-bell" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="M8 16a2 2 0 001.985-1.75c.017-.137-.097-.25-.235-.25h-3.5c-.138 0-.252.113-.235.25A2 2 0 008 16z"></path><path fill-rule="evenodd" d="M8 1.5A3.5 3.5 0 004.5 5v2.947c0 .346-.102.683-.294.97l-1.703 2.556a.018.018 0 00-.003.01l.001.006c0 .002.002.004.004.006a.017.017 0 00.006.004l.007.001h10.964l.007-.001a.016.016 0 00.006-.004.016.016 0 00.004-.006l.001-.007a.017.017 0 00-.003-.01l-1.703-2.554a1.75 1.75 0 01-.294-.97V5A3.5 3.5 0 008 1.5zM3 5a5 5 0 0110 0v2.947c0 .05.015.098.042.139l1.703 2.555A1.518 1.518 0 0113.482 13H2.518a1.518 1.518 0 01-1.263-2.36l1.703-2.554A.25.25 0 003 7.947V5z"></path></svg>
      </a>
    </notification-indicator>

    </div>


    <div class="Header-item position-relative d-none d-md-flex">
      <details class="details-overlay details-reset">
  <summary class="Header-link"
      aria-label="Create new…"
      data-ga-click="Header, create new, icon:add">
      <svg class="octicon octicon-plus" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M8 2a.75.75 0 01.75.75v4.5h4.5a.75.75 0 010 1.5h-4.5v4.5a.75.75 0 01-1.5 0v-4.5h-4.5a.75.75 0 010-1.5h4.5v-4.5A.75.75 0 018 2z"></path></svg> <span class="dropdown-caret"></span>
  </summary>
  <details-menu class="dropdown-menu dropdown-menu-sw">
    
<a role="menuitem" class="dropdown-item" href="/new" data-ga-click="Header, create new repository">
  New repository
</a>

  <a role="menuitem" class="dropdown-item" href="/new/import" data-ga-click="Header, import a repository">
    Import repository
  </a>

<a role="menuitem" class="dropdown-item" href="https://gist.github.com/" data-ga-click="Header, create new gist">
  New gist
</a>

  <a role="menuitem" class="dropdown-item" href="/organizations/new" data-ga-click="Header, create new organization">
    New organization
  </a>


  <div role="none" class="dropdown-divider"></div>
  <div class="dropdown-header">
    <span title="OneForward/TACpp">This repository</span>
  </div>
    <a role="menuitem" class="dropdown-item" href="/OneForward/TACpp/issues/new/choose" data-ga-click="Header, create new issue" data-skip-pjax>
      New issue
    </a>


  </details-menu>
</details>

    </div>

    <div class="Header-item position-relative mr-0 d-none d-md-flex">
      
  <details class="details-overlay details-reset js-feature-preview-indicator-container" data-feature-preview-indicator-src="/users/905355494/feature_preview/indicator_check">

  <summary class="Header-link"
    aria-label="View profile and more"
    data-ga-click="Header, show menu, icon:avatar">
    <img
  alt="@905355494"
  width="20"
  height="20"
  src="https://avatars3.githubusercontent.com/u/59958814?s=60&amp;v=4"
  class="avatar avatar-user " />

      <span class="feature-preview-indicator js-feature-preview-indicator" style="top: 10px;" hidden></span>
    <span class="dropdown-caret"></span>
  </summary>
  <details-menu class="dropdown-menu dropdown-menu-sw" style="width: 180px" >
    <div class="header-nav-current-user css-truncate"><a role="menuitem" class="no-underline user-profile-link px-3 pt-2 pb-2 mb-n2 mt-n1 d-block" href="/905355494" data-ga-click="Header, go to profile, text:Signed in as">Signed in as <strong class="css-truncate-target">905355494</strong></a></div>
    <div role="none" class="dropdown-divider"></div>

      <div class="pl-3 pr-3 f6 user-status-container js-user-status-context lh-condensed" data-url="/users/status?compact=1&amp;link_mentions=0&amp;truncate=1">
        
<div class="js-user-status-container rounded-1 px-2 py-1 mt-2 border"
  data-team-hovercards-enabled>
  <details class="js-user-status-details details-reset details-overlay details-overlay-dark">
    <summary class="btn-link btn-block link-gray no-underline js-toggle-user-status-edit toggle-user-status-edit "
      role="menuitem" data-hydro-click="{&quot;event_type&quot;:&quot;user_profile.click&quot;,&quot;payload&quot;:{&quot;profile_user_id&quot;:16881692,&quot;target&quot;:&quot;EDIT_USER_STATUS&quot;,&quot;user_id&quot;:59958814,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;}}" data-hydro-click-hmac="164d16a87050cecb58b5a30a56b225212756b2dcfb392933c941637fa55b9f54">
      <div class="d-flex flex-items-center flex-items-stretch">
        <div class="f6 lh-condensed user-status-header d-flex user-status-emoji-only-header circle">
          <div class="user-status-emoji-container flex-shrink-0 mr-2 d-flex flex-items-center flex-justify-center lh-condensed-ultra v-align-bottom">
            <svg class="octicon octicon-smiley" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.5 8a6.5 6.5 0 1113 0 6.5 6.5 0 01-13 0zM8 0a8 8 0 100 16A8 8 0 008 0zM5 8a1 1 0 100-2 1 1 0 000 2zm7-1a1 1 0 11-2 0 1 1 0 012 0zM5.32 9.636a.75.75 0 011.038.175l.007.009c.103.118.22.222.35.31.264.178.683.37 1.285.37.602 0 1.02-.192 1.285-.371.13-.088.247-.192.35-.31l.007-.008a.75.75 0 111.222.87l-.614-.431c.614.43.614.431.613.431v.001l-.001.002-.002.003-.005.007-.014.019a1.984 1.984 0 01-.184.213c-.16.166-.338.316-.53.445-.63.418-1.37.638-2.127.629-.946 0-1.652-.308-2.126-.63a3.32 3.32 0 01-.715-.657l-.014-.02-.005-.006-.002-.003v-.002h-.001l.613-.432-.614.43a.75.75 0 01.183-1.044h.001z"></path></svg>
          </div>
        </div>
        <div class="
          
           user-status-message-wrapper f6 min-width-0"
           style="line-height: 20px;" >
          <div class="css-truncate css-truncate-target width-fit text-gray-dark text-left">
              <span class="text-gray">Set status</span>
          </div>
        </div>
      </div>
    </summary>
    <details-dialog class="details-dialog rounded-1 anim-fade-in fast Box Box--overlay" role="dialog" tabindex="-1">
      <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="position-relative flex-auto js-user-status-form" action="/users/status?circle=0&amp;compact=1&amp;link_mentions=0&amp;truncate=1" accept-charset="UTF-8" method="post"><input type="hidden" name="_method" value="put" /><input type="hidden" name="authenticity_token" value="57Nhz1pcjtxt4KWOfxnRxYoleelQ7Rb1r+K+CtDUKcrv0kyXkyLlkLgo1ZFS/GAsj5oo3QqGSTwcaCUHAFbllA==" />
        <div class="Box-header bg-gray border-bottom p-3">
          <button class="Box-btn-octicon js-toggle-user-status-edit btn-octicon float-right" type="reset" aria-label="Close dialog" data-close-dialog>
            <svg class="octicon octicon-x" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M3.72 3.72a.75.75 0 011.06 0L8 6.94l3.22-3.22a.75.75 0 111.06 1.06L9.06 8l3.22 3.22a.75.75 0 11-1.06 1.06L8 9.06l-3.22 3.22a.75.75 0 01-1.06-1.06L6.94 8 3.72 4.78a.75.75 0 010-1.06z"></path></svg>
          </button>
          <h3 class="Box-title f5 text-bold text-gray-dark">Edit status</h3>
        </div>
        <input type="hidden" name="emoji" class="js-user-status-emoji-field" value="">
        <input type="hidden" name="organization_id" class="js-user-status-org-id-field" value="">
        <div class="px-3 py-2 text-gray-dark">
          <div class="js-characters-remaining-container position-relative mt-2">
            <div class="input-group d-table form-group my-0 js-user-status-form-group">
              <span class="input-group-button d-table-cell v-align-middle" style="width: 1%">
                <button type="button" aria-label="Choose an emoji" class="btn-outline btn js-toggle-user-status-emoji-picker btn-open-emoji-picker p-0">
                  <span class="js-user-status-original-emoji" hidden></span>
                  <span class="js-user-status-custom-emoji"></span>
                  <span class="js-user-status-no-emoji-icon" >
                    <svg class="octicon octicon-smiley" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.5 8a6.5 6.5 0 1113 0 6.5 6.5 0 01-13 0zM8 0a8 8 0 100 16A8 8 0 008 0zM5 8a1 1 0 100-2 1 1 0 000 2zm7-1a1 1 0 11-2 0 1 1 0 012 0zM5.32 9.636a.75.75 0 011.038.175l.007.009c.103.118.22.222.35.31.264.178.683.37 1.285.37.602 0 1.02-.192 1.285-.371.13-.088.247-.192.35-.31l.007-.008a.75.75 0 111.222.87l-.614-.431c.614.43.614.431.613.431v.001l-.001.002-.002.003-.005.007-.014.019a1.984 1.984 0 01-.184.213c-.16.166-.338.316-.53.445-.63.418-1.37.638-2.127.629-.946 0-1.652-.308-2.126-.63a3.32 3.32 0 01-.715-.657l-.014-.02-.005-.006-.002-.003v-.002h-.001l.613-.432-.614.43a.75.75 0 01.183-1.044h.001z"></path></svg>
                  </span>
                </button>
              </span>
              <text-expander keys=": @" data-mention-url="/autocomplete/user-suggestions" data-emoji-url="/autocomplete/emoji">
                <input
                  type="text"
                  autocomplete="off"
                  data-no-org-url="/autocomplete/user-suggestions"
                  data-org-url="/suggestions?mention_suggester=1"
                  data-maxlength="80"
                  class="d-table-cell width-full form-control js-user-status-message-field js-characters-remaining-field"
                  placeholder="What's happening?"
                  name="message"
                  value=""
                  aria-label="What is your current status?">
              </text-expander>
              <div class="error">Could not update your status, please try again.</div>
            </div>
            <div style="margin-left: 53px" class="my-1 text-small label-characters-remaining js-characters-remaining" data-suffix="remaining" hidden>
              80 remaining
            </div>
          </div>
          <include-fragment class="js-user-status-emoji-picker" data-url="/users/status/emoji"></include-fragment>
          <div class="overflow-auto ml-n3 mr-n3 px-3 border-bottom" style="max-height: 33vh">
            <div class="user-status-suggestions js-user-status-suggestions collapsed overflow-hidden">
              <h4 class="f6 text-normal my-3">Suggestions:</h4>
              <div class="mx-3 mt-2 clearfix">
                  <div class="float-left col-6">
                      <button type="button" value=":palm_tree:" class="d-flex flex-items-baseline flex-items-stretch lh-condensed f6 btn-link link-gray no-underline js-predefined-user-status mb-1">
                        <div class="emoji-status-width mr-2 v-align-middle js-predefined-user-status-emoji">
                          <g-emoji alias="palm_tree" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f334.png">🌴</g-emoji>
                        </div>
                        <div class="d-flex flex-items-center no-underline js-predefined-user-status-message ws-normal text-left" style="border-left: 1px solid transparent">
                          On vacation
                        </div>
                      </button>
                      <button type="button" value=":face_with_thermometer:" class="d-flex flex-items-baseline flex-items-stretch lh-condensed f6 btn-link link-gray no-underline js-predefined-user-status mb-1">
                        <div class="emoji-status-width mr-2 v-align-middle js-predefined-user-status-emoji">
                          <g-emoji alias="face_with_thermometer" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f912.png">🤒</g-emoji>
                        </div>
                        <div class="d-flex flex-items-center no-underline js-predefined-user-status-message ws-normal text-left" style="border-left: 1px solid transparent">
                          Out sick
                        </div>
                      </button>
                  </div>
                  <div class="float-left col-6">
                      <button type="button" value=":house:" class="d-flex flex-items-baseline flex-items-stretch lh-condensed f6 btn-link link-gray no-underline js-predefined-user-status mb-1">
                        <div class="emoji-status-width mr-2 v-align-middle js-predefined-user-status-emoji">
                          <g-emoji alias="house" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f3e0.png">🏠</g-emoji>
                        </div>
                        <div class="d-flex flex-items-center no-underline js-predefined-user-status-message ws-normal text-left" style="border-left: 1px solid transparent">
                          Working from home
                        </div>
                      </button>
                      <button type="button" value=":dart:" class="d-flex flex-items-baseline flex-items-stretch lh-condensed f6 btn-link link-gray no-underline js-predefined-user-status mb-1">
                        <div class="emoji-status-width mr-2 v-align-middle js-predefined-user-status-emoji">
                          <g-emoji alias="dart" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/1f3af.png">🎯</g-emoji>
                        </div>
                        <div class="d-flex flex-items-center no-underline js-predefined-user-status-message ws-normal text-left" style="border-left: 1px solid transparent">
                          Focusing
                        </div>
                      </button>
                  </div>
              </div>
            </div>
            <div class="user-status-limited-availability-container">
              <div class="form-checkbox my-0">
                <input type="checkbox" name="limited_availability" value="1" class="js-user-status-limited-availability-checkbox" data-default-message="I may be slow to respond." aria-describedby="limited-availability-help-text-truncate-true-compact-true" id="limited-availability-truncate-true-compact-true">
                <label class="d-block f5 text-gray-dark mb-1" for="limited-availability-truncate-true-compact-true">
                  Busy
                </label>
                <p class="note" id="limited-availability-help-text-truncate-true-compact-true">
                  When others mention you, assign you, or request your review,
                  GitHub will let them know that you have limited availability.
                </p>
              </div>
            </div>
          </div>
          <div class="d-inline-block f5 mr-2 pt-3 pb-2" >
  <div class="d-inline-block mr-1">
    Clear status
  </div>

  <details class="js-user-status-expire-drop-down f6 dropdown details-reset details-overlay d-inline-block mr-2">
    <summary class="btn btn-sm v-align-baseline" aria-haspopup="true">
      <div class="js-user-status-expiration-interval-selected d-inline-block v-align-baseline">
        Never
      </div>
      <div class="dropdown-caret"></div>
    </summary>

    <ul class="dropdown-menu dropdown-menu-se pl-0 overflow-auto" style="width: 220px; max-height: 15.5em">
      <li>
        <button type="button" class="btn-link dropdown-item js-user-status-expire-button ws-normal" title="Never">
          <span class="d-inline-block text-bold mb-1">Never</span>
          <div class="f6 lh-condensed">Keep this status until you clear your status or edit your status.</div>
        </button>
      </li>
      <li class="dropdown-divider" role="none"></li>
        <li>
          <button type="button" class="btn-link dropdown-item ws-normal js-user-status-expire-button" title="in 30 minutes" value="2020-09-28T14:41:11+08:00">
            in 30 minutes
          </button>
        </li>
        <li>
          <button type="button" class="btn-link dropdown-item ws-normal js-user-status-expire-button" title="in 1 hour" value="2020-09-28T15:11:11+08:00">
            in 1 hour
          </button>
        </li>
        <li>
          <button type="button" class="btn-link dropdown-item ws-normal js-user-status-expire-button" title="in 4 hours" value="2020-09-28T18:11:11+08:00">
            in 4 hours
          </button>
        </li>
        <li>
          <button type="button" class="btn-link dropdown-item ws-normal js-user-status-expire-button" title="today" value="2020-09-28T23:59:59+08:00">
            today
          </button>
        </li>
        <li>
          <button type="button" class="btn-link dropdown-item ws-normal js-user-status-expire-button" title="this week" value="2020-10-04T23:59:59+08:00">
            this week
          </button>
        </li>
    </ul>
  </details>
  <input class="js-user-status-expiration-date-input" type="hidden" name="expires_at" value="">
</div>

          <include-fragment class="js-user-status-org-picker" data-url="/users/status/organizations"></include-fragment>
        </div>
        <div class="d-flex flex-items-center flex-justify-between p-3 border-top">
          <button type="submit" disabled class="width-full btn btn-primary mr-2 js-user-status-submit">
            Set status
          </button>
          <button type="button" disabled class="width-full js-clear-user-status-button btn ml-2 ">
            Clear status
          </button>
        </div>
</form>    </details-dialog>
  </details>
</div>

      </div>
      <div role="none" class="dropdown-divider"></div>

    <a role="menuitem" class="dropdown-item" href="/905355494" data-ga-click="Header, go to profile, text:your profile" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;YOUR_PROFILE&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="c3a83368fef9cefe2a09836fd238bc27593f4e1a81a687592901f276df2d30e9" >Your profile</a>

    <a role="menuitem" class="dropdown-item" href="/905355494?tab=repositories" data-ga-click="Header, go to repositories, text:your repositories" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;YOUR_REPOSITORIES&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="9b3c5d2001e1466ceec7d754dd0754215fda78990408c428db5149231113a93e" >Your repositories</a>



    <a role="menuitem" class="dropdown-item" href="/905355494?tab=projects" data-ga-click="Header, go to projects, text:your projects" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;YOUR_PROJECTS&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="60cc62cedeecc336a83d95692d1d6ff1bb5d2da5542d26e42534fca2296ee466" >Your projects</a>


    <a role="menuitem" class="dropdown-item" href="/905355494?tab=stars" data-ga-click="Header, go to starred repos, text:your stars" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;YOUR_STARS&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="3132430fbdc29579426728338274f90a8dba6be75c0a4c4ee2db248c24fdf237" >Your stars</a>
      <a role="menuitem" class="dropdown-item" href="https://gist.github.com/mine" data-ga-click="Header, your gists, text:your gists" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;YOUR_GISTS&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="ead04c9bdf155a173e7958f88e9f8b4f421c41e152b846e3a231be04abc5cb41" >Your gists</a>





    <div role="none" class="dropdown-divider"></div>
      <a role="menuitem" class="dropdown-item" href="/settings/billing" data-ga-click="Header, go to billing, text:upgrade" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;UPGRADE&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="ff56f08d57e8aa3e13e1f1477853b76ab8c7d671f76a63cd47c8fbaa628431ee" >Upgrade</a>
      
<div id="feature-enrollment-toggle" class="hide-sm hide-md feature-preview-details position-relative">
  <button
    type="button"
    class="dropdown-item btn-link"
    role="menuitem"
    data-feature-preview-trigger-url="/users/905355494/feature_previews"
    data-feature-preview-close-details="{&quot;event_type&quot;:&quot;feature_preview.clicks.close_modal&quot;,&quot;payload&quot;:{&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}"
    data-feature-preview-close-hmac="d46cd3bc991d9a2e2d3164ed4044c986cd77d530f73819b8b4d68135c6c955e7"
    data-hydro-click="{&quot;event_type&quot;:&quot;feature_preview.clicks.open_modal&quot;,&quot;payload&quot;:{&quot;link_location&quot;:&quot;user_dropdown&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}"
    data-hydro-click-hmac="b737a10fe88b2067ddf6e09f17ecc4ed056ad3e566cd5fb61bf9c81c3e52bff1"
  >
    Feature preview
  </button>
    <span class="feature-preview-indicator js-feature-preview-indicator" hidden></span>
</div>

    <a role="menuitem" class="dropdown-item" href="https://docs.github.com" data-ga-click="Header, go to help, text:help" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;HELP&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="687068c1b13ec6528a0df27508d79fab590f9db3012c6cf912937994a0b98656" >Help</a>
    <a role="menuitem" class="dropdown-item" href="/settings/profile" data-ga-click="Header, go to settings, icon:settings" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;SETTINGS&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="13c5af50136d348146263a80d07744dfdbbe2f22ac29cb6578c1282c8fd672f1" >Settings</a>
    <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="logout-form" action="/logout" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="7iEHWYeHdDlPTZ+gCZ6pAEeOCaDkq65SC2mp0OVVaQ4RjzngfmQSpZ53Y88rD6yuncB+ikfR1nuvrTOltDODqA==" />
      
      <button type="submit" class="dropdown-item dropdown-signout" data-ga-click="Header, sign out, icon:logout" data-hydro-click="{&quot;event_type&quot;:&quot;global_header.user_menu_dropdown.click&quot;,&quot;payload&quot;:{&quot;request_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;target&quot;:&quot;SIGN_OUT&quot;,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="a7930e8138dd6b699886bdb567f085c2a423dce9f889b297fbb23113182d8c1a"  role="menuitem">
        Sign out
      </button>
      <input type="text" name="required_field_9969" hidden="hidden" class="form-control" /><input type="hidden" name="timestamp" value="1601273471774" class="form-control" /><input type="hidden" name="timestamp_secret" value="bebec151d8880655eee06ef55d49081a4b354bcb9a520122bc32ec9bb154da91" class="form-control" />
</form>  </details-menu>
</details>

    </div>
</header>

          

    </div>

  <div id="start-of-content" class="show-on-focus"></div>






    <div id="js-flash-container">


  <template class="js-flash-template">
    <div class="flash flash-full  {{ className }}">
  <div class=" px-2" >
    <button class="flash-close js-flash-close" type="button" aria-label="Dismiss this message">
      <svg class="octicon octicon-x" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M3.72 3.72a.75.75 0 011.06 0L8 6.94l3.22-3.22a.75.75 0 111.06 1.06L9.06 8l3.22 3.22a.75.75 0 11-1.06 1.06L8 9.06l-3.22 3.22a.75.75 0 01-1.06-1.06L6.94 8 3.72 4.78a.75.75 0 010-1.06z"></path></svg>
    </button>
    
      <div>{{ message }}</div>

  </div>
</div>
  </template>
</div>


  

  <include-fragment class="js-notification-shelf-include-fragment" data-base-src="https://github.com/notifications/beta/shelf"></include-fragment>



  <div
    class="application-main "
    data-commit-hovercards-enabled
    data-discussion-hovercards-enabled
    data-issue-and-pr-hovercards-enabled
  >
        <div itemscope itemtype="http://schema.org/SoftwareSourceCode" class="">
    <main  >
      

    






  


  <div class="bg-gray-light pt-3 hide-full-screen mb-5">

      <div class="d-flex mb-3 px-3 px-md-4 px-lg-5">

        <div class="flex-auto min-width-0 width-fit mr-3">
            <h1 class=" d-flex flex-wrap flex-items-center break-word f3 text-normal">
    <svg class="octicon octicon-repo text-gray" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"></path></svg>
  <span class="author ml-2 flex-self-stretch" itemprop="author">
    <a class="url fn" rel="author" data-hovercard-type="user" data-hovercard-url="/users/OneForward/hovercard" data-octo-click="hovercard-link-click" data-octo-dimensions="link_type:self" href="/OneForward">OneForward</a>
  </span>
  <span class="mx-1 flex-self-stretch">/</span>
  <strong itemprop="name" class="mr-2 flex-self-stretch">
    <a data-pjax="#js-repo-pjax-container" href="/OneForward/TACpp">TACpp</a>
  </strong>
  
</h1>


        </div>

          <ul class="pagehead-actions flex-shrink-0 d-none d-md-inline" style="padding: 2px 0;">

  <li>
            <form data-remote="true" class="d-flex js-social-form js-social-container" action="/notifications/subscribe" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="dFMg9yJ51eAPX3Vmx18hcQw8Hj1bz3ENM+5RiovPn8fmaL4bBLkruuN5cdSGMCRoZox+HBtJME8QhmRzSMO6QA==" />      <input type="hidden" name="repository_id" value="294645801">

      <details class="details-reset details-overlay select-menu hx_rsm">
        <summary class="btn btn-sm btn-with-count" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;WATCH_BUTTON&quot;,&quot;repository_id&quot;:294645801,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="5cbce0fdd83eb5d88b6ffacfbca2068c441a67ca22a7aaa30860d4caa2bdf153" data-ga-click="Repository, click Watch settings, action:blob#show">          <span data-menu-button>
              <svg height="16" class="octicon octicon-eye" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.679 7.932c.412-.621 1.242-1.75 2.366-2.717C5.175 4.242 6.527 3.5 8 3.5c1.473 0 2.824.742 3.955 1.715 1.124.967 1.954 2.096 2.366 2.717a.119.119 0 010 .136c-.412.621-1.242 1.75-2.366 2.717C10.825 11.758 9.473 12.5 8 12.5c-1.473 0-2.824-.742-3.955-1.715C2.92 9.818 2.09 8.69 1.679 8.068a.119.119 0 010-.136zM8 2c-1.981 0-3.67.992-4.933 2.078C1.797 5.169.88 6.423.43 7.1a1.619 1.619 0 000 1.798c.45.678 1.367 1.932 2.637 3.024C4.329 13.008 6.019 14 8 14c1.981 0 3.67-.992 4.933-2.078 1.27-1.091 2.187-2.345 2.637-3.023a1.619 1.619 0 000-1.798c-.45-.678-1.367-1.932-2.637-3.023C11.671 2.992 9.981 2 8 2zm0 8a2 2 0 100-4 2 2 0 000 4z"></path></svg>
              Watch
          </span>
          <span class="dropdown-caret"></span>
</summary>        <details-menu
          class="select-menu-modal position-absolute mt-5"
          style="z-index: 99;">
          <div class="select-menu-header">
            <span class="select-menu-title">Notifications</span>
          </div>
          <div class="select-menu-list">
            <button type="submit" name="do" value="included" class="select-menu-item width-full" aria-checked="true" role="menuitemradio">
              <svg class="octicon octicon-check select-menu-item-icon" height="16" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path></svg>
              <div class="select-menu-item-text">
                <span class="select-menu-item-heading">Not watching</span>
                <span class="description">Be notified only when participating or @mentioned.</span>
                <span class="hidden-select-button-text" data-menu-button-contents>
                  <svg height="16" class="octicon octicon-eye" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.679 7.932c.412-.621 1.242-1.75 2.366-2.717C5.175 4.242 6.527 3.5 8 3.5c1.473 0 2.824.742 3.955 1.715 1.124.967 1.954 2.096 2.366 2.717a.119.119 0 010 .136c-.412.621-1.242 1.75-2.366 2.717C10.825 11.758 9.473 12.5 8 12.5c-1.473 0-2.824-.742-3.955-1.715C2.92 9.818 2.09 8.69 1.679 8.068a.119.119 0 010-.136zM8 2c-1.981 0-3.67.992-4.933 2.078C1.797 5.169.88 6.423.43 7.1a1.619 1.619 0 000 1.798c.45.678 1.367 1.932 2.637 3.024C4.329 13.008 6.019 14 8 14c1.981 0 3.67-.992 4.933-2.078 1.27-1.091 2.187-2.345 2.637-3.023a1.619 1.619 0 000-1.798c-.45-.678-1.367-1.932-2.637-3.023C11.671 2.992 9.981 2 8 2zm0 8a2 2 0 100-4 2 2 0 000 4z"></path></svg>
                  Watch
                </span>
              </div>
            </button>

            <button type="submit" name="do" value="release_only" class="select-menu-item width-full" aria-checked="false" role="menuitemradio">
              <svg class="octicon octicon-check select-menu-item-icon" height="16" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path></svg>
              <div class="select-menu-item-text">
                <span class="select-menu-item-heading">Releases only</span>
                <span class="description">Be notified of new releases, and when participating or @mentioned.</span>
                <span class="hidden-select-button-text" data-menu-button-contents>
                  <svg height="16" class="octicon octicon-eye" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.679 7.932c.412-.621 1.242-1.75 2.366-2.717C5.175 4.242 6.527 3.5 8 3.5c1.473 0 2.824.742 3.955 1.715 1.124.967 1.954 2.096 2.366 2.717a.119.119 0 010 .136c-.412.621-1.242 1.75-2.366 2.717C10.825 11.758 9.473 12.5 8 12.5c-1.473 0-2.824-.742-3.955-1.715C2.92 9.818 2.09 8.69 1.679 8.068a.119.119 0 010-.136zM8 2c-1.981 0-3.67.992-4.933 2.078C1.797 5.169.88 6.423.43 7.1a1.619 1.619 0 000 1.798c.45.678 1.367 1.932 2.637 3.024C4.329 13.008 6.019 14 8 14c1.981 0 3.67-.992 4.933-2.078 1.27-1.091 2.187-2.345 2.637-3.023a1.619 1.619 0 000-1.798c-.45-.678-1.367-1.932-2.637-3.023C11.671 2.992 9.981 2 8 2zm0 8a2 2 0 100-4 2 2 0 000 4z"></path></svg>
                  Unwatch releases
                </span>
              </div>
            </button>

            <button type="submit" name="do" value="subscribed" class="select-menu-item width-full" aria-checked="false" role="menuitemradio">
              <svg class="octicon octicon-check select-menu-item-icon" height="16" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path></svg>
              <div class="select-menu-item-text">
                <span class="select-menu-item-heading">Watching</span>
                <span class="description">Be notified of all conversations.</span>
                <span class="hidden-select-button-text" data-menu-button-contents>
                  <svg class="octicon octicon-eye v-align-text-bottom" height="16" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.679 7.932c.412-.621 1.242-1.75 2.366-2.717C5.175 4.242 6.527 3.5 8 3.5c1.473 0 2.824.742 3.955 1.715 1.124.967 1.954 2.096 2.366 2.717a.119.119 0 010 .136c-.412.621-1.242 1.75-2.366 2.717C10.825 11.758 9.473 12.5 8 12.5c-1.473 0-2.824-.742-3.955-1.715C2.92 9.818 2.09 8.69 1.679 8.068a.119.119 0 010-.136zM8 2c-1.981 0-3.67.992-4.933 2.078C1.797 5.169.88 6.423.43 7.1a1.619 1.619 0 000 1.798c.45.678 1.367 1.932 2.637 3.024C4.329 13.008 6.019 14 8 14c1.981 0 3.67-.992 4.933-2.078 1.27-1.091 2.187-2.345 2.637-3.023a1.619 1.619 0 000-1.798c-.45-.678-1.367-1.932-2.637-3.023C11.671 2.992 9.981 2 8 2zm0 8a2 2 0 100-4 2 2 0 000 4z"></path></svg>
                  Unwatch
                </span>
              </div>
            </button>

            <button type="submit" name="do" value="ignore" class="select-menu-item width-full" aria-checked="false" role="menuitemradio">
              <svg class="octicon octicon-check select-menu-item-icon" height="16" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path></svg>
              <div class="select-menu-item-text">
                <span class="select-menu-item-heading">Ignoring</span>
                <span class="description">Never be notified.</span>
                <span class="hidden-select-button-text" data-menu-button-contents>
                  <svg height="16" class="octicon octicon-bell-slash" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M8 1.5c-.997 0-1.895.416-2.534 1.086A.75.75 0 014.38 1.55 5 5 0 0113 5v2.373a.75.75 0 01-1.5 0V5A3.5 3.5 0 008 1.5zM4.182 4.31L1.19 2.143a.75.75 0 10-.88 1.214L3 5.305v2.642a.25.25 0 01-.042.139L1.255 10.64A1.518 1.518 0 002.518 13h11.108l1.184.857a.75.75 0 10.88-1.214l-1.375-.996a1.196 1.196 0 00-.013-.01L4.198 4.321a.733.733 0 00-.016-.011zm7.373 7.19L4.5 6.391v1.556c0 .346-.102.683-.294.97l-1.703 2.556a.018.018 0 00-.003.01.015.015 0 00.005.012.017.017 0 00.006.004l.007.001h9.037zM8 16a2 2 0 001.985-1.75c.017-.137-.097-.25-.235-.25h-3.5c-.138 0-.252.113-.235.25A2 2 0 008 16z"></path></svg>
                  Stop ignoring
                </span>
              </div>
            </button>
          </div>
        </details-menu>
      </details>
        <a class="social-count js-social-count"
          href="/OneForward/TACpp/watchers"
          aria-label="1 user is watching this repository">
          1
        </a>
</form>
  </li>

  <li>
        <div class="js-toggler-container js-social-container starring-container ">
    <form class="starred js-social-form" action="/OneForward/TACpp/unstar" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="ODO+/NjVz7lBRbDwGUIz5DyflTjyPWGh5RjseHM4YfrSDg7kroLHoIMrchUmav2/5jEjNcmcEYG9IJaALE59Yg==" />
      <input type="hidden" name="context" value="repository"></input>
      <button type="submit" class="btn btn-sm btn-with-count  js-toggler-target" aria-label="Unstar this repository" title="Unstar OneForward/TACpp" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;UNSTAR_BUTTON&quot;,&quot;repository_id&quot;:294645801,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="732e8487bebbba74d375a93e92df0deb3f3969a2023b5b9ddbfedda60b673236" data-ga-click="Repository, click unstar button, action:blob#show; text:Unstar">        <svg height="16" class="octicon octicon-star-fill" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25z"></path></svg>
        Unstar
</button>        <a class="social-count js-social-count" href="/OneForward/TACpp/stargazers"
           aria-label="2 users starred this repository">
           2
        </a>
</form>
    <form class="unstarred js-social-form" action="/OneForward/TACpp/star" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="0n5RFMKYPEpkJFqDaQRw8wxA3bCKWs15UchZKy57/6mB9nNO7txlkTV4NB6Z5OA28OExtQ2J6/B+keecuzoalw==" />
      <input type="hidden" name="context" value="repository"></input>
      <button type="submit" class="btn btn-sm btn-with-count  js-toggler-target" aria-label="Unstar this repository" title="Star OneForward/TACpp" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;STAR_BUTTON&quot;,&quot;repository_id&quot;:294645801,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="a47b9e62d59f8cc60d555edf53577ac5d845c7d751768b02d7f61a574e7b780e" data-ga-click="Repository, click star button, action:blob#show; text:Star">        <svg height="16" class="octicon octicon-star" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M8 .25a.75.75 0 01.673.418l1.882 3.815 4.21.612a.75.75 0 01.416 1.279l-3.046 2.97.719 4.192a.75.75 0 01-1.088.791L8 12.347l-3.766 1.98a.75.75 0 01-1.088-.79l.72-4.194L.818 6.374a.75.75 0 01.416-1.28l4.21-.611L7.327.668A.75.75 0 018 .25zm0 2.445L6.615 5.5a.75.75 0 01-.564.41l-3.097.45 2.24 2.184a.75.75 0 01.216.664l-.528 3.084 2.769-1.456a.75.75 0 01.698 0l2.77 1.456-.53-3.084a.75.75 0 01.216-.664l2.24-2.183-3.096-.45a.75.75 0 01-.564-.41L8 2.694v.001z"></path></svg>
        Star
</button>        <a class="social-count js-social-count" href="/OneForward/TACpp/stargazers"
           aria-label="2 users starred this repository">
          2
        </a>
</form>  </div>

  </li>

  <li>
            <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="btn-with-count" action="/OneForward/TACpp/fork" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="hj1+7B1yCAttZinXRSFUP7bvNjoopCg7g1dcZoClg2o11kgIdNIc7N/1AlFu5jFnHdLPf1VKpaNSNdRLv9bYVw==" />
              <button class="btn btn-sm btn-with-count" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;FORK_BUTTON&quot;,&quot;repository_id&quot;:294645801,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="55457ab9933b2669effa00d96d46669eb6f000a8ce8e357f0ffecb4ed1357a2c" data-ga-click="Repository, show fork modal, action:blob#show; text:Fork" type="submit" title="Fork your own copy of OneForward/TACpp to your account" aria-label="Fork your own copy of OneForward/TACpp to your account">                <svg class="octicon octicon-repo-forked" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M5 3.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm0 2.122a2.25 2.25 0 10-1.5 0v.878A2.25 2.25 0 005.75 8.5h1.5v2.128a2.251 2.251 0 101.5 0V8.5h1.5a2.25 2.25 0 002.25-2.25v-.878a2.25 2.25 0 10-1.5 0v.878a.75.75 0 01-.75.75h-4.5A.75.75 0 015 6.25v-.878zm3.75 7.378a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm3-8.75a.75.75 0 100-1.5.75.75 0 000 1.5z"></path></svg>
                Fork
</button></form>
      <a href="/OneForward/TACpp/network/members" class="social-count"
         aria-label="3 users forked this repository">
        3
      </a>
  </li>
</ul>

      </div>
        
<nav aria-label="Repository" data-pjax="#js-repo-pjax-container" class="js-repo-nav js-sidenav-container-pjax js-responsive-underlinenav overflow-hidden UnderlineNav px-3 px-md-4 px-lg-5 bg-gray-light">
  <ul class="UnderlineNav-body list-style-none ">
          <li class="d-flex">
        <a class="js-selected-navigation-item selected UnderlineNav-item hx_underlinenav-item no-wrap js-responsive-underlinenav-item" data-tab-item="code-tab" data-hotkey="g c" data-ga-click="Repository, Navigation click, Code tab" aria-current="page" data-selected-links="repo_source repo_downloads repo_commits repo_releases repo_tags repo_branches repo_packages repo_deployments /OneForward/TACpp" href="/OneForward/TACpp">
              <svg classes="UnderlineNav-octicon" display="none inline" height="16" class="octicon octicon-code UnderlineNav-octicon d-none d-sm-inline" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M4.72 3.22a.75.75 0 011.06 1.06L2.06 8l3.72 3.72a.75.75 0 11-1.06 1.06L.47 8.53a.75.75 0 010-1.06l4.25-4.25zm6.56 0a.75.75 0 10-1.06 1.06L13.94 8l-3.72 3.72a.75.75 0 101.06 1.06l4.25-4.25a.75.75 0 000-1.06l-4.25-4.25z"></path></svg>
            <span data-content="Code">Code</span>
              <span title="Not available" class="Counter "></span>
</a>      </li>
      <li class="d-flex">
        <a class="js-selected-navigation-item UnderlineNav-item hx_underlinenav-item no-wrap js-responsive-underlinenav-item" data-tab-item="issues-tab" data-hotkey="g i" data-ga-click="Repository, Navigation click, Issues tab" data-selected-links="repo_issues repo_labels repo_milestones /OneForward/TACpp/issues" href="/OneForward/TACpp/issues">
              <svg classes="UnderlineNav-octicon" display="none inline" height="16" class="octicon octicon-issue-opened UnderlineNav-octicon d-none d-sm-inline" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M8 1.5a6.5 6.5 0 100 13 6.5 6.5 0 000-13zM0 8a8 8 0 1116 0A8 8 0 010 8zm9 3a1 1 0 11-2 0 1 1 0 012 0zm-.25-6.25a.75.75 0 00-1.5 0v3.5a.75.75 0 001.5 0v-3.5z"></path></svg>
            <span data-content="Issues">Issues</span>
              <span title="0" hidden="hidden" class="Counter ">0</span>
</a>      </li>
      <li class="d-flex">
        <a class="js-selected-navigation-item UnderlineNav-item hx_underlinenav-item no-wrap js-responsive-underlinenav-item" data-tab-item="pull-requests-tab" data-hotkey="g p" data-ga-click="Repository, Navigation click, Pull requests tab" data-selected-links="repo_pulls checks /OneForward/TACpp/pulls" href="/OneForward/TACpp/pulls">
              <svg classes="UnderlineNav-octicon" display="none inline" height="16" class="octicon octicon-git-pull-request UnderlineNav-octicon d-none d-sm-inline" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.177 3.073L9.573.677A.25.25 0 0110 .854v4.792a.25.25 0 01-.427.177L7.177 3.427a.25.25 0 010-.354zM3.75 2.5a.75.75 0 100 1.5.75.75 0 000-1.5zm-2.25.75a2.25 2.25 0 113 2.122v5.256a2.251 2.251 0 11-1.5 0V5.372A2.25 2.25 0 011.5 3.25zM11 2.5h-1V4h1a1 1 0 011 1v5.628a2.251 2.251 0 101.5 0V5A2.5 2.5 0 0011 2.5zm1 10.25a.75.75 0 111.5 0 .75.75 0 01-1.5 0zM3.75 12a.75.75 0 100 1.5.75.75 0 000-1.5z"></path></svg>
            <span data-content="Pull requests">Pull requests</span>
              <span title="0" hidden="hidden" class="Counter ">0</span>
</a>      </li>
      <li class="d-flex">
        <a class="js-selected-navigation-item UnderlineNav-item hx_underlinenav-item no-wrap js-responsive-underlinenav-item" data-tab-item="actions-tab" data-hotkey="g a" data-ga-click="Repository, Navigation click, Actions tab" data-selected-links="repo_actions /OneForward/TACpp/actions" href="/OneForward/TACpp/actions">
              <svg classes="UnderlineNav-octicon" display="none inline" height="16" class="octicon octicon-play UnderlineNav-octicon d-none d-sm-inline" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.5 8a6.5 6.5 0 1113 0 6.5 6.5 0 01-13 0zM8 0a8 8 0 100 16A8 8 0 008 0zM6.379 5.227A.25.25 0 006 5.442v5.117a.25.25 0 00.379.214l4.264-2.559a.25.25 0 000-.428L6.379 5.227z"></path></svg>
            <span data-content="Actions">Actions</span>
              <span title="Not available" class="Counter "></span>
</a>      </li>
      <li class="d-flex">
        <a class="js-selected-navigation-item UnderlineNav-item hx_underlinenav-item no-wrap js-responsive-underlinenav-item" data-tab-item="projects-tab" data-hotkey="g b" data-ga-click="Repository, Navigation click, Projects tab" data-selected-links="repo_projects new_repo_project repo_project /OneForward/TACpp/projects" href="/OneForward/TACpp/projects">
              <svg classes="UnderlineNav-octicon" display="none inline" height="16" class="octicon octicon-project UnderlineNav-octicon d-none d-sm-inline" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.75 0A1.75 1.75 0 000 1.75v12.5C0 15.216.784 16 1.75 16h12.5A1.75 1.75 0 0016 14.25V1.75A1.75 1.75 0 0014.25 0H1.75zM1.5 1.75a.25.25 0 01.25-.25h12.5a.25.25 0 01.25.25v12.5a.25.25 0 01-.25.25H1.75a.25.25 0 01-.25-.25V1.75zM11.75 3a.75.75 0 00-.75.75v7.5a.75.75 0 001.5 0v-7.5a.75.75 0 00-.75-.75zm-8.25.75a.75.75 0 011.5 0v5.5a.75.75 0 01-1.5 0v-5.5zM8 3a.75.75 0 00-.75.75v3.5a.75.75 0 001.5 0v-3.5A.75.75 0 008 3z"></path></svg>
            <span data-content="Projects">Projects</span>
              <span title="0" hidden="hidden" class="Counter ">0</span>
</a>      </li>
      <li class="d-flex">
        <a class="js-selected-navigation-item UnderlineNav-item hx_underlinenav-item no-wrap js-responsive-underlinenav-item" data-tab-item="wiki-tab" data-hotkey="g w" data-ga-click="Repository, Navigation click, Wikis tab" data-selected-links="repo_wiki /OneForward/TACpp/wiki" href="/OneForward/TACpp/wiki">
              <svg classes="UnderlineNav-octicon" display="none inline" height="16" class="octicon octicon-book UnderlineNav-octicon d-none d-sm-inline" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M0 1.75A.75.75 0 01.75 1h4.253c1.227 0 2.317.59 3 1.501A3.744 3.744 0 0111.006 1h4.245a.75.75 0 01.75.75v10.5a.75.75 0 01-.75.75h-4.507a2.25 2.25 0 00-1.591.659l-.622.621a.75.75 0 01-1.06 0l-.622-.621A2.25 2.25 0 005.258 13H.75a.75.75 0 01-.75-.75V1.75zm8.755 3a2.25 2.25 0 012.25-2.25H14.5v9h-3.757c-.71 0-1.4.201-1.992.572l.004-7.322zm-1.504 7.324l.004-5.073-.002-2.253A2.25 2.25 0 005.003 2.5H1.5v9h3.757a3.75 3.75 0 011.994.574z"></path></svg>
            <span data-content="Wiki">Wiki</span>
              <span title="Not available" class="Counter "></span>
</a>      </li>
      <li class="d-flex">
        <a class="js-selected-navigation-item UnderlineNav-item hx_underlinenav-item no-wrap js-responsive-underlinenav-item" data-tab-item="security-tab" data-hotkey="g s" data-ga-click="Repository, Navigation click, Security tab" data-selected-links="security overview alerts policy token_scanning code_scanning /OneForward/TACpp/security" href="/OneForward/TACpp/security">
              <svg classes="UnderlineNav-octicon" display="none inline" height="16" class="octicon octicon-shield UnderlineNav-octicon d-none d-sm-inline" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.467.133a1.75 1.75 0 011.066 0l5.25 1.68A1.75 1.75 0 0115 3.48V7c0 1.566-.32 3.182-1.303 4.682-.983 1.498-2.585 2.813-5.032 3.855a1.7 1.7 0 01-1.33 0c-2.447-1.042-4.049-2.357-5.032-3.855C1.32 10.182 1 8.566 1 7V3.48a1.75 1.75 0 011.217-1.667l5.25-1.68zm.61 1.429a.25.25 0 00-.153 0l-5.25 1.68a.25.25 0 00-.174.238V7c0 1.358.275 2.666 1.057 3.86.784 1.194 2.121 2.34 4.366 3.297a.2.2 0 00.154 0c2.245-.956 3.582-2.104 4.366-3.298C13.225 9.666 13.5 8.36 13.5 7V3.48a.25.25 0 00-.174-.237l-5.25-1.68zM9 10.5a1 1 0 11-2 0 1 1 0 012 0zm-.25-5.75a.75.75 0 10-1.5 0v3a.75.75 0 001.5 0v-3z"></path></svg>
            <span data-content="Security">Security</span>
              <include-fragment src="/OneForward/TACpp/security/overall-count" accept="text/fragment+html"></include-fragment>
</a>      </li>
      <li class="d-flex">
        <a class="js-selected-navigation-item UnderlineNav-item hx_underlinenav-item no-wrap js-responsive-underlinenav-item" data-tab-item="insights-tab" data-ga-click="Repository, Navigation click, Insights tab" data-selected-links="repo_graphs repo_contributors dependency_graph dependabot_updates pulse people /OneForward/TACpp/pulse" href="/OneForward/TACpp/pulse">
              <svg classes="UnderlineNav-octicon" display="none inline" height="16" class="octicon octicon-graph UnderlineNav-octicon d-none d-sm-inline" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.5 1.75a.75.75 0 00-1.5 0v12.5c0 .414.336.75.75.75h14.5a.75.75 0 000-1.5H1.5V1.75zm14.28 2.53a.75.75 0 00-1.06-1.06L10 7.94 7.53 5.47a.75.75 0 00-1.06 0L3.22 8.72a.75.75 0 001.06 1.06L7 7.06l2.47 2.47a.75.75 0 001.06 0l5.25-5.25z"></path></svg>
            <span data-content="Insights">Insights</span>
              <span title="Not available" class="Counter "></span>
</a>      </li>

</ul>        <div class="position-absolute right-0 pr-3 pr-md-4 pr-lg-5 js-responsive-underlinenav-overflow" style="visibility:hidden;">
      <details class="details-overlay details-reset position-relative">
  <summary role="button">
    <div class="UnderlineNav-item mr-0 border-0">
            <svg class="octicon octicon-kebab-horizontal" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="M8 9a1.5 1.5 0 100-3 1.5 1.5 0 000 3zM1.5 9a1.5 1.5 0 100-3 1.5 1.5 0 000 3zm13 0a1.5 1.5 0 100-3 1.5 1.5 0 000 3z"></path></svg>
            <span class="sr-only">More</span>
          </div>
</summary>  <div>
    <details-menu role="menu" class="dropdown-menu dropdown-menu-sw ">
  
            <ul>
                <li data-menu-item="code-tab" hidden>
                  <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links=" /OneForward/TACpp" href="/OneForward/TACpp">
                    Code
</a>                </li>
                <li data-menu-item="issues-tab" hidden>
                  <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links=" /OneForward/TACpp/issues" href="/OneForward/TACpp/issues">
                    Issues
</a>                </li>
                <li data-menu-item="pull-requests-tab" hidden>
                  <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links=" /OneForward/TACpp/pulls" href="/OneForward/TACpp/pulls">
                    Pull requests
</a>                </li>
                <li data-menu-item="actions-tab" hidden>
                  <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links=" /OneForward/TACpp/actions" href="/OneForward/TACpp/actions">
                    Actions
</a>                </li>
                <li data-menu-item="projects-tab" hidden>
                  <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links=" /OneForward/TACpp/projects" href="/OneForward/TACpp/projects">
                    Projects
</a>                </li>
                <li data-menu-item="wiki-tab" hidden>
                  <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links=" /OneForward/TACpp/wiki" href="/OneForward/TACpp/wiki">
                    Wiki
</a>                </li>
                <li data-menu-item="security-tab" hidden>
                  <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links=" /OneForward/TACpp/security" href="/OneForward/TACpp/security">
                    Security
</a>                </li>
                <li data-menu-item="insights-tab" hidden>
                  <a role="menuitem" class="js-selected-navigation-item dropdown-item" data-selected-links=" /OneForward/TACpp/pulse" href="/OneForward/TACpp/pulse">
                    Insights
</a>                </li>
            </ul>

</details-menu>
</div></details>    </div>

</nav>
  </div>

<div class="container-xl clearfix new-discussion-timeline px-3 px-md-4 px-lg-5">
  <div class="repository-content " >

    
      
  


    <a class="d-none js-permalink-shortcut" data-hotkey="y" href="/OneForward/TACpp/blob/9746d3a066a8e6dbb8c97d5ce9f15cd520cd6e09/tutorials/CppFormat.md">Permalink</a>

    <!-- blob contrib key: blob_contributors:v22:39db33f8905c155b49c400558ef0a85ac0e9f70be2e991297f80b909f16f93e5 -->
    

    <div class="d-flex flex-items-start flex-shrink-0 pb-3 flex-wrap flex-md-nowrap flex-justify-between flex-md-justify-start">
      
<div class="position-relative">
  <details class="details-reset details-overlay mr-0 mb-0 " id="branch-select-menu">
    <summary class="btn css-truncate"
            data-hotkey="w"
            title="Switch branches or tags">
      <svg text="gray" height="16" class="octicon octicon-git-branch text-gray" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M11.75 2.5a.75.75 0 100 1.5.75.75 0 000-1.5zm-2.25.75a2.25 2.25 0 113 2.122V6A2.5 2.5 0 0110 8.5H6a1 1 0 00-1 1v1.128a2.251 2.251 0 11-1.5 0V5.372a2.25 2.25 0 111.5 0v1.836A2.492 2.492 0 016 7h4a1 1 0 001-1v-.628A2.25 2.25 0 019.5 3.25zM4.25 12a.75.75 0 100 1.5.75.75 0 000-1.5zM3.5 3.25a.75.75 0 111.5 0 .75.75 0 01-1.5 0z"></path></svg>
      <span class="css-truncate-target" data-menu-button>master</span>
      <span class="dropdown-caret"></span>
    </summary>

    <details-menu class="SelectMenu SelectMenu--hasFilter" src="/OneForward/TACpp/refs/master/tutorials/CppFormat.md?source_action=show&amp;source_controller=blob" preload>
      <div class="SelectMenu-modal">
        <include-fragment class="SelectMenu-loading" aria-label="Menu is loading">
          <svg class="octicon octicon-octoface anim-pulse" height="32" viewBox="0 0 24 24" version="1.1" width="32" aria-hidden="true"><path d="M7.75 11c-.69 0-1.25.56-1.25 1.25v1.5a1.25 1.25 0 102.5 0v-1.5C9 11.56 8.44 11 7.75 11zm1.27 4.5a.469.469 0 01.48-.5h5a.47.47 0 01.48.5c-.116 1.316-.759 2.5-2.98 2.5s-2.864-1.184-2.98-2.5zm7.23-4.5c-.69 0-1.25.56-1.25 1.25v1.5a1.25 1.25 0 102.5 0v-1.5c0-.69-.56-1.25-1.25-1.25z"></path><path fill-rule="evenodd" d="M21.255 3.82a1.725 1.725 0 00-2.141-1.195c-.557.16-1.406.44-2.264.866-.78.386-1.647.93-2.293 1.677A18.442 18.442 0 0012 5c-.93 0-1.784.059-2.569.17-.645-.74-1.505-1.28-2.28-1.664a13.876 13.876 0 00-2.265-.866 1.725 1.725 0 00-2.141 1.196 23.645 23.645 0 00-.69 3.292c-.125.97-.191 2.07-.066 3.112C1.254 11.882 1 13.734 1 15.527 1 19.915 3.13 23 12 23c8.87 0 11-3.053 11-7.473 0-1.794-.255-3.647-.99-5.29.127-1.046.06-2.15-.066-3.125a23.652 23.652 0 00-.689-3.292zM20.5 14c.5 3.5-1.5 6.5-8.5 6.5s-9-3-8.5-6.5c.583-4 3-6 8.5-6s7.928 2 8.5 6z"></path></svg>
        </include-fragment>
      </div>
    </details-menu>
  </details>

</div>

      <h2 id="blob-path" class="breadcrumb flex-auto min-width-0 text-normal mx-0 mx-md-3 width-full width-md-auto flex-order-1 flex-md-order-none mt-3 mt-md-0">
        <span class="js-repo-root text-bold"><span class="js-path-segment d-inline-block wb-break-all"><a data-pjax="true" href="/OneForward/TACpp"><span>TACpp</span></a></span></span><span class="separator">/</span><span class="js-path-segment d-inline-block wb-break-all"><a data-pjax="true" href="/OneForward/TACpp/tree/master/tutorials"><span>tutorials</span></a></span><span class="separator">/</span><strong class="final-path">CppFormat.md</strong>
      </h2>
      <a href="/OneForward/TACpp/find/master"
            class="js-pjax-capture-input btn mr-2 d-none d-md-block"
            data-pjax
            data-hotkey="t">
        Go to file
      </a>

      <details id="blob-more-options-details" class="details-overlay details-reset position-relative">
  <summary role="button">
    <svg aria-label="More options" height="16" class="octicon octicon-kebab-horizontal" viewBox="0 0 16 16" version="1.1" width="16" role="img"><path d="M8 9a1.5 1.5 0 100-3 1.5 1.5 0 000 3zM1.5 9a1.5 1.5 0 100-3 1.5 1.5 0 000 3zm13 0a1.5 1.5 0 100-3 1.5 1.5 0 000 3z"></path></svg>
</summary>  <div>
    <ul class="dropdown-menu dropdown-menu-sw">
            <li class="d-block d-md-none">
              <a class="dropdown-item d-flex flex-items-baseline" data-hydro-click="{&quot;event_type&quot;:&quot;repository.click&quot;,&quot;payload&quot;:{&quot;target&quot;:&quot;FIND_FILE_BUTTON&quot;,&quot;repository_id&quot;:294645801,&quot;originating_url&quot;:&quot;https://github.com/OneForward/TACpp/blob/master/tutorials/CppFormat.md&quot;,&quot;user_id&quot;:59958814}}" data-hydro-click-hmac="565dbfe9365620b275ce61d9c7fb349bfd031d782a932888f35d69efab2410bb" data-ga-click="Repository, find file, location:repo overview" data-hotkey="t" data-pjax="true" href="/OneForward/TACpp/find/master">
                <span class="flex-auto">Go to file</span>
                <span class="text-small text-gray" aria-hidden="true">T</span>
</a>            </li>
            <li data-toggle-for="blob-more-options-details">
              <button type="button" data-toggle-for="jumpto-line-details-dialog" class="btn-link dropdown-item">
                <span class="d-flex flex-items-baseline">
                  <span class="flex-auto">Go to line</span>
                  <span class="text-small text-gray" aria-hidden="true">L</span>
                </span>
              </button>
            </li>
            <li class="dropdown-divider" role="none"></li>
            <li>
              <clipboard-copy value="tutorials/CppFormat.md" class="dropdown-item cursor-pointer" data-toggle-for="blob-more-options-details">
                Copy path
              </clipboard-copy>
            </li>
          </ul>
</div></details>    </div>



    <div class="Box d-flex flex-column flex-shrink-0 mb-3">
      
  <div class="Box-header Box-header--blue Details js-details-container">
      <div class="d-flex flex-items-center">
        <span class="flex-shrink-0 ml-n1 mr-n1 mt-n1 mb-n1">
          <a rel="author" data-skip-pjax="true" href="/OneForward"><img class="avatar avatar-user" skip_hovercard="20" src="https://avatars3.githubusercontent.com/u/16881692?s=48&amp;v=4" width="24" height="24" alt="@OneForward" /></a>
        </span>
        <div class="flex-1 d-flex flex-items-center ml-3 min-width-0">
          <div class="css-truncate css-truncate-overflow">
            <a class="text-bold link-gray-dark" rel="author" href="/OneForward">OneForward</a>

              <span>
                <a data-pjax="true" title="show src code" class="link-gray" href="/OneForward/TACpp/commit/9746d3a066a8e6dbb8c97d5ce9f15cd520cd6e09">show src code</a>
              </span>
          </div>


          <span class="ml-2">
            <include-fragment accept="text/fragment+html" src="/OneForward/TACpp/commit/9746d3a066a8e6dbb8c97d5ce9f15cd520cd6e09/rollup?direction=e" class="d-inline"></include-fragment>
          </span>
        </div>
        <div class="ml-3 d-flex flex-shrink-0 flex-items-center flex-justify-end text-gray no-wrap">
          <span class="d-none d-md-inline">
            <span>Latest commit</span>
            <a class="text-small text-mono link-gray" href="/OneForward/TACpp/commit/9746d3a066a8e6dbb8c97d5ce9f15cd520cd6e09" data-pjax>9746d3a</a>
            <span itemprop="dateModified"><relative-time datetime="2020-09-27T11:29:34Z" class="no-wrap">Sep 27, 2020</relative-time></span>
          </span>

          <a data-pjax href="/OneForward/TACpp/commits/master/tutorials/CppFormat.md" class="ml-3 no-wrap link-gray-dark no-underline">
            <svg text="gray" height="16" class="octicon octicon-history text-gray" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.643 3.143L.427 1.927A.25.25 0 000 2.104V5.75c0 .138.112.25.25.25h3.646a.25.25 0 00.177-.427L2.715 4.215a6.5 6.5 0 11-1.18 4.458.75.75 0 10-1.493.154 8.001 8.001 0 101.6-5.684zM7.75 4a.75.75 0 01.75.75v2.992l2.028.812a.75.75 0 01-.557 1.392l-2.5-1A.75.75 0 017 8.25v-3.5A.75.75 0 017.75 4z"></path></svg>
            <span class="d-none d-sm-inline">
              <strong>History</strong>
            </span>
          </a>
        </div>
      </div>

  </div>

  <div class="Box-body d-flex flex-items-center flex-auto border-bottom-0 flex-wrap" >
    <details class="details-reset details-overlay details-overlay-dark lh-default text-gray-dark float-left mr-3" id="blob_contributors_box">
      <summary class="link-gray-dark">
        <svg text="gray" height="16" class="octicon octicon-people text-gray" viewBox="0 0 16 16" version="1.1" width="16" aria-hidden="true"><path fill-rule="evenodd" d="M5.5 3.5a2 2 0 100 4 2 2 0 000-4zM2 5.5a3.5 3.5 0 115.898 2.549 5.507 5.507 0 013.034 4.084.75.75 0 11-1.482.235 4.001 4.001 0 00-7.9 0 .75.75 0 01-1.482-.236A5.507 5.507 0 013.102 8.05 3.49 3.49 0 012 5.5zM11 4a.75.75 0 100 1.5 1.5 1.5 0 01.666 2.844.75.75 0 00-.416.672v.352a.75.75 0 00.574.73c1.2.289 2.162 1.2 2.522 2.372a.75.75 0 101.434-.44 5.01 5.01 0 00-2.56-3.012A3 3 0 0011 4z"></path></svg>
        <strong>1</strong>
        
        contributor
      </summary>
      <details-dialog
        class="Box Box--overlay d-flex flex-column anim-fade-in fast"
        aria-label="Users who have contributed to this file"
        src="/OneForward/TACpp/contributors-list/master/tutorials/CppFormat.md" preload>
        <div class="Box-header">
          <button class="Box-btn-octicon btn-octicon float-right" type="button" aria-label="Close dialog" data-close-dialog>
            <svg class="octicon octicon-x" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M3.72 3.72a.75.75 0 011.06 0L8 6.94l3.22-3.22a.75.75 0 111.06 1.06L9.06 8l3.22 3.22a.75.75 0 11-1.06 1.06L8 9.06l-3.22 3.22a.75.75 0 01-1.06-1.06L6.94 8 3.72 4.78a.75.75 0 010-1.06z"></path></svg>
          </button>
          <h3 class="Box-title">
            Users who have contributed to this file
          </h3>
        </div>
        <include-fragment class="octocat-spinner my-3" aria-label="Loading..."></include-fragment>
      </details-dialog>
    </details>
  </div>
    </div>






    <div class="Box mt-3 position-relative
      ">
      
<div class="Box-header py-2 d-flex flex-column flex-shrink-0 flex-md-row flex-md-items-center">
  <div class="text-mono f6 flex-auto pr-3 flex-order-2 flex-md-order-1 mt-2 mt-md-0">

      320 lines (229 sloc)
      <span class="file-info-divider"></span>
    12.7 KB
  </div>

  <div class="d-flex py-1 py-md-0 flex-auto flex-order-1 flex-md-order-2 flex-sm-grow-0 flex-justify-between">

    <div class="BtnGroup">
      <a href="/OneForward/TACpp/raw/master/tutorials/CppFormat.md" id="raw-url" role="button" class="btn btn-sm BtnGroup-item ">Raw</a>
        <a href="/OneForward/TACpp/blame/master/tutorials/CppFormat.md" data-hotkey="b" role="button" class="btn js-update-url-with-hash btn-sm BtnGroup-item ">Blame</a>
    </div>

    <div>
          <a class="btn-octicon tooltipped tooltipped-nw js-remove-unless-platform"
             data-platforms="windows,mac"
             href="x-github-client://openRepo/https://github.com/OneForward/TACpp?branch=master&amp;filepath=tutorials%2FCppFormat.md"
             aria-label="Open this file in GitHub Desktop"
             data-ga-click="Repository, open with desktop">
              <svg class="octicon octicon-device-desktop" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M1.75 2.5h12.5a.25.25 0 01.25.25v7.5a.25.25 0 01-.25.25H1.75a.25.25 0 01-.25-.25v-7.5a.25.25 0 01.25-.25zM14.25 1H1.75A1.75 1.75 0 000 2.75v7.5C0 11.216.784 12 1.75 12h3.727c-.1 1.041-.52 1.872-1.292 2.757A.75.75 0 004.75 16h6.5a.75.75 0 00.565-1.243c-.772-.885-1.193-1.716-1.292-2.757h3.727A1.75 1.75 0 0016 10.25v-7.5A1.75 1.75 0 0014.25 1zM9.018 12H6.982a5.72 5.72 0 01-.765 2.5h3.566a5.72 5.72 0 01-.765-2.5z"></path></svg>
          </a>

          <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="inline-form js-update-url-with-hash" action="/OneForward/TACpp/edit/master/tutorials/CppFormat.md" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="j9KpXsQViQoqb2bNTBoxRCLyC5TnCk31Nm8j3xoY14ykHsgD5AyphE9atGUaQj8HkkJtFA0wU6siZGty3k57mg==" />
            <button class="btn-octicon tooltipped tooltipped-nw" type="submit"
              aria-label="Edit the file in your fork of this project" data-hotkey="e" data-disable-with>
              <svg class="octicon octicon-pencil" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M11.013 1.427a1.75 1.75 0 012.474 0l1.086 1.086a1.75 1.75 0 010 2.474l-8.61 8.61c-.21.21-.47.364-.756.445l-3.251.93a.75.75 0 01-.927-.928l.929-3.25a1.75 1.75 0 01.445-.758l8.61-8.61zm1.414 1.06a.25.25 0 00-.354 0L10.811 3.75l1.439 1.44 1.263-1.263a.25.25 0 000-.354l-1.086-1.086zM11.189 6.25L9.75 4.81l-6.286 6.287a.25.25 0 00-.064.108l-.558 1.953 1.953-.558a.249.249 0 00.108-.064l6.286-6.286z"></path></svg>
            </button>
</form>
          <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="inline-form" action="/OneForward/TACpp/delete/master/tutorials/CppFormat.md" accept-charset="UTF-8" method="post"><input type="hidden" name="authenticity_token" value="ozx20TykZEBHEee+s1Sd9H4YxcMs5HZbVTk5IaT0lJWVsgYDjii6L88hBZoi3cI++ydHmJ9Ack1b6u9KmA74tA==" />
            <button class="btn-octicon btn-octicon-danger tooltipped tooltipped-nw" type="submit"
              aria-label="Delete the file in your fork of this project" data-disable-with>
              <svg class="octicon octicon-trashcan" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M6.5 1.75a.25.25 0 01.25-.25h2.5a.25.25 0 01.25.25V3h-3V1.75zm4.5 0V3h2.25a.75.75 0 010 1.5H2.75a.75.75 0 010-1.5H5V1.75C5 .784 5.784 0 6.75 0h2.5C10.216 0 11 .784 11 1.75zM4.496 6.675a.75.75 0 10-1.492.15l.66 6.6A1.75 1.75 0 005.405 15h5.19c.9 0 1.652-.681 1.741-1.576l.66-6.6a.75.75 0 00-1.492-.149l-.66 6.6a.25.25 0 01-.249.225h-5.19a.25.25 0 01-.249-.225l-.66-6.6z"></path></svg>
            </button>
</form>    </div>
  </div>
</div>



      
  <div id="readme" class="Box-body readme blob js-code-block-container p-5 p-xl-6 gist-border-0">
    <article class="markdown-body entry-content container-lg" itemprop="text"><h1><a id="user-content-c-流控制库-iomanip--与-c-风格-printf-的对比" class="anchor" aria-hidden="true" href="#c-流控制库-iomanip--与-c-风格-printf-的对比"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>C++ 流控制库 <code>&lt;iomanip&gt;</code>  与 C 风格 <code>printf</code> 的对比</h1>
<p>示例代码在 <a href="https://github.com/OneForward/TACpp/blob/master/tutorials/codes/test_base.cpp">test_base.cpp</a>, <a href="https://github.com/OneForward/TACpp/blob/master/tutorials/codes/test_fill_width.cpp">test_fill_width.cpp</a></p>
<ul>
<li><a href="#c-%E6%B5%81%E6%8E%A7%E5%88%B6%E5%BA%93-iomanip-%E4%B8%8E-c-%E9%A3%8E%E6%A0%BC-printf-%E7%9A%84%E5%AF%B9%E6%AF%94">C++ 流控制库 <code>&lt;iomanip&gt;</code>  与 C 风格 <code>printf</code> 的对比</a>
<ul>
<li><a href="#%E6%95%B4%E6%95%B0-n-%E8%BF%9B%E5%88%B6">整数 $n$ 进制</a></li>
<li><a href="#%E5%AE%BD%E5%BA%A6%E5%AF%B9%E9%BD%90%E5%A1%AB%E5%85%85">宽度、对齐、填充</a>
<ul>
<li><a href="#%E4%BD%BF%E7%94%A8-printf">使用 <code>printf</code></a></li>
<li><a href="#%E4%BD%BF%E7%94%A8%E6%B5%81%E6%8E%A7%E5%88%B6%E5%BA%93">使用流控制库</a></li>
<li><a href="#%E6%B5%AE%E7%82%B9%E6%95%B0%E5%AE%9A%E5%AE%BD%E5%AF%B9%E9%BD%90">浮点数定宽、对齐</a></li>
<li><a href="#%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%AE%9A%E5%AE%BD%E5%AF%B9%E9%BD%90">字符串定宽、对齐</a></li>
<li><a href="#%E6%B5%AE%E7%82%B9%E6%95%B0%E7%B2%BE%E5%BA%A6%E8%AE%BE%E7%BD%AE">浮点数精度设置</a></li>
</ul>
</li>
<li><a href="#%E5%85%B3%E4%BA%8E%E4%B8%A4%E7%A7%8D%E6%A0%BC%E5%BC%8F%E6%8E%A7%E5%88%B6%E7%9A%84%E8%AF%84%E8%AE%BA">关于两种格式控制的评论</a></li>
<li><a href="#printf-%E8%AF%A6%E8%A7%A3"><code>printf</code> 详解</a>
<ul>
<li><a href="#%E5%87%BD%E6%95%B0%E5%8E%9F%E5%9E%8B">函数原型</a></li>
<li><a href="#%E6%A0%BC%E5%BC%8F%E5%8C%96%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%9A%84%E5%8F%82%E6%95%B0">格式化字符串的参数</a></li>
<li><a href="#%E4%BE%8B%E5%AD%90">例子</a></li>
</ul>
</li>
</ul>
</li>
</ul>
<h2><a id="user-content-整数-n-进制" class="anchor" aria-hidden="true" href="#整数-n-进制"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>整数 $n$ 进制</h2>
<ul>
<li>
<p><code>printf</code> 使用格式标识符 <code>%x %o %d</code> 来表明进制。</p>
<ul>
<li><code>%x</code> ：代表将数字格式化为16进制形式</li>
<li><code>%o</code> ：代表将数字格式化为8进制形式</li>
<li><code>%d</code> ：代表将数字格式化为10进制形式</li>
</ul>
</li>
<li>
<p>流控制库 <code>&lt;iomanip&gt;</code> 可以使用 <code>hex oct dec</code> 来设置进制。或者使用 <code>std::setbase(int base)</code>。注意，如果传入的不是 8、10、16，则输出<strong>十进制</strong>。</p>
<ul>
<li><code>hex</code> , <code>setbase(16)</code></li>
<li><code>oct</code> , <code>setbase(8)</code></li>
<li><code>dec</code> , <code>setbase(10)</code></li>
</ul>
</li>
</ul>
<div class="highlight highlight-source-c++"><pre><span class="pl-k">int</span> num = <span class="pl-c1">15</span>;

<span class="pl-en">printf</span>( <span class="pl-s"><span class="pl-pds">"</span>十六进制：%x<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, num);
<span class="pl-en">printf</span>( <span class="pl-s"><span class="pl-pds">"</span>八进制：%o<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, num);
<span class="pl-en">printf</span>( <span class="pl-s"><span class="pl-pds">"</span>十进制：%d<span class="pl-cce">\n\n</span><span class="pl-pds">"</span></span>, num);


cout &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>十六进制：<span class="pl-pds">"</span></span> &lt;&lt; hex &lt;&lt; num &lt;&lt; endl
     &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>八进制：<span class="pl-pds">"</span></span> &lt;&lt; oct &lt;&lt; num &lt;&lt; endl
     &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>十进制：<span class="pl-pds">"</span></span> &lt;&lt; dec &lt;&lt; num &lt;&lt; endl &lt;&lt; endl;

cout &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>十六进制：<span class="pl-pds">"</span></span> &lt;&lt; setbase(<span class="pl-c1">16</span>) &lt;&lt; num &lt;&lt; endl
     &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>八进制：<span class="pl-pds">"</span></span> &lt;&lt; setbase(<span class="pl-c1">8</span>) &lt;&lt; num &lt;&lt; endl
     &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>十进制：<span class="pl-pds">"</span></span> &lt;&lt; setbase(<span class="pl-c1">10</span>) &lt;&lt; num &lt;&lt; endl &lt;&lt; endl;</pre></div>
<p>输出都是</p>
<pre><code>十六进制：f
八进制：17
十进制：15
</code></pre>
<h2><a id="user-content-宽度对齐填充" class="anchor" aria-hidden="true" href="#宽度对齐填充"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>宽度、对齐、填充</h2>
<h3><a id="user-content-使用-printf" class="anchor" aria-hidden="true" href="#使用-printf"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>使用 <code>printf</code></h3>
<p><code>printf</code> 中格式化字符串的形式如下，</p>
<p><code>%[flags][width][.precision][length]specifier</code></p>
<p>解释几个常见的用法，更详细的规则见 <a href="#printf-%E8%AF%A6%E8%A7%A3"><code>printf</code> 详解</a></p>
<ul>
<li>中括号 <code>[]</code> 内的 设置都是可选的。</li>
<li><code>specifier</code>: 类型说明符，必须设置。常见的
<ul>
<li><code>'d'</code>、<code>'i'</code> 代表整型</li>
<li><code>'g'</code>、<code>'f'</code> 代表浮点数</li>
<li><code>'c'</code> 代表字符 char</li>
<li><code>'s'</code> 代表字符串</li>
</ul>
</li>
<li><code>flags</code>: 字符,（用在定宽情形下）
<ul>
<li>默认右对齐。</li>
<li><code>'-'</code> 代表左对齐，</li>
<li><code>'0'</code> 代表用 0 填充。</li>
</ul>
</li>
<li><code>width</code>: 数字，设置 字符串宽度。</li>
<li><code>.precision</code>: <code>'.'</code> 加数字，表示小数点后保留几位小数。</li>
</ul>
<p>注意，<code>printf</code> 的限制很大，例如 “填补字符” 只有 <code>'0'</code> 和 空格 <code>' '</code> ，使用 <code>'0'</code> 时还只能使用右对齐。因为左对齐的 <code>'-'</code> 会排斥填补的 <code>'0'</code> 。</p>
<p>例子</p>
<ul>
<li>
<p>例如 <code>%-10g</code> 代表将浮点数字格式化为宽度为10，左对齐的字符串。</p>
</li>
<li>
<p>例如 <code>%010.3f</code> 代表将浮点数字格式化为保留3位小数、宽度为10，右对齐，前缀填充了0的字符串。</p>
</li>
<li>
<p>例如 <code>%-010g</code> 由于左对齐的 <code>'-'</code> 会排斥填补的 <code>'0'</code>，因此这里的效果等价于<code>%-10g</code>。</p>
</li>
</ul>
<h3><a id="user-content-使用流控制库" class="anchor" aria-hidden="true" href="#使用流控制库"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>使用流控制库</h3>
<p>相比之下，流控制库 <code>&lt;iomanip&gt;</code>  使用</p>
<ul>
<li><code>setw(int n)</code> : 设置宽度</li>
<li><code>setfill(char ch)</code>: 填充字符</li>
<li><code>left</code> : 左对齐</li>
<li><code>right</code> : 右对齐</li>
<li><code>precision(int n)</code> : 设置有效数字个数</li>
<li><code>fixed</code> : 与 <code>precision</code> 一起用，设置小数点后有效数字的个数</li>
</ul>
<p>其填补更加灵活，可以自定义填补字符，而且 “左右对齐” 和 “填补字符” 可以自由组合。</p>
<p>注意，流控制库 <code>&lt;iomanip&gt;</code>  在设置最小<strong>宽度</strong>时使用的流控制符 <code>std::setw(int n)</code> <strong>仅对下一个输出有效</strong>，因此需要不断使用。</p>
<h3><a id="user-content-浮点数定宽对齐" class="anchor" aria-hidden="true" href="#浮点数定宽对齐"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>浮点数定宽、对齐</h3>
<div class="highlight highlight-source-c++"><pre><span class="pl-k">double</span> num = <span class="pl-c1">4.0</span>; 
<span class="pl-en">printf</span>( <span class="pl-s"><span class="pl-pds">"</span>宽度为10，右对齐：[%10g]<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>
        <span class="pl-s"><span class="pl-pds">"</span>宽度为10，左对齐：[%-10g]<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>
        <span class="pl-s"><span class="pl-pds">"</span>宽度为10，右对齐，空白补0：[%010.g]<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>
        <span class="pl-s"><span class="pl-pds">"</span><span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, num, num, num);

cout &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>宽度为10，右对齐：[<span class="pl-pds">"</span></span> 
     &lt;&lt; setw(<span class="pl-c1">10</span>) &lt;&lt; num &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>]<span class="pl-pds">"</span></span> &lt;&lt; endl
     
     &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>宽度为10，左对齐：[<span class="pl-pds">"</span></span> &lt;&lt; left
     &lt;&lt; setw(<span class="pl-c1">10</span>) &lt;&lt; num &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>]<span class="pl-pds">"</span></span> &lt;&lt; endl
     &lt;&lt; resetiosflags(ios::left)
     
     &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>宽度为10，右对齐，空白补0：[<span class="pl-pds">"</span></span> &lt;&lt; right
     &lt;&lt; setfill(<span class="pl-s"><span class="pl-pds">'</span>0<span class="pl-pds">'</span></span>) &lt;&lt; setw(<span class="pl-c1">10</span>) &lt;&lt; num &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>]<span class="pl-pds">"</span></span> &lt;&lt; endl
     &lt;&lt; resetiosflags(ios::right)
                                 
     &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>宽度为10，左对齐，空白补*：[<span class="pl-pds">"</span></span> &lt;&lt; left
     &lt;&lt; setfill(<span class="pl-s"><span class="pl-pds">'</span>*<span class="pl-pds">'</span></span>) &lt;&lt; setw(<span class="pl-c1">10</span>) &lt;&lt; num &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>]<span class="pl-pds">"</span></span> &lt;&lt; endl
     &lt;&lt; resetiosflags(ios::left);</pre></div>
<p>输出</p>
<pre><code>宽度为10，右对齐：[         4]
宽度为10，左对齐：[4         ]
宽度为10，右对齐，空白补0：[0000000004]      

宽度为10，右对齐：[         4]
宽度为10，左对齐：[4         ]
宽度为10，右对齐，空白补0：[0000000004]      
宽度为10，左对齐，空白补*：[4*********]
</code></pre>
<h3><a id="user-content-字符串定宽对齐" class="anchor" aria-hidden="true" href="#字符串定宽对齐"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>字符串定宽、对齐</h3>
<div class="highlight highlight-source-c++"><pre><span class="pl-k">auto</span> s = <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>;

<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span><span class="pl-cce">\n</span><span class="pl-pds">"</span></span>);
<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>宽度为10，右对齐: [%10s] <span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>);
<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>宽度为10，左对齐: [%-10s] <span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>);   
<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span><span class="pl-cce">\n</span><span class="pl-pds">"</span></span>);


cout &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>宽度为10，右对齐：[<span class="pl-pds">"</span></span> &lt;&lt; setfill(<span class="pl-s"><span class="pl-pds">'</span> <span class="pl-pds">'</span></span>)
        &lt;&lt; setw(<span class="pl-c1">10</span>) &lt;&lt; s &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>]<span class="pl-pds">"</span></span> &lt;&lt; endl
        
        &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>宽度为10，左对齐：[<span class="pl-pds">"</span></span> &lt;&lt; left
        &lt;&lt; setw(<span class="pl-c1">10</span>) &lt;&lt; s &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>]<span class="pl-pds">"</span></span> &lt;&lt; endl
        &lt;&lt; resetiosflags(ios::left);</pre></div>
<p>输出</p>
<pre><code>宽度为10，右对齐: [     Hello] 
宽度为10，左对齐: [Hello     ]

宽度为10，右对齐：[     Hello]
宽度为10，左对齐：[Hello     ]
</code></pre>
<h3><a id="user-content-浮点数精度设置" class="anchor" aria-hidden="true" href="#浮点数精度设置"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>浮点数精度设置</h3>
<div class="highlight highlight-source-c++"><pre><span class="pl-k">double</span> x = <span class="pl-c1">20.0</span> / <span class="pl-c1">3</span>;

<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span><span class="pl-cce">\n</span><span class="pl-pds">"</span></span>);
<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>保留3位小数: %.3f<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, x);
<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>保留3位小数，宽度10且左对齐: [%-10.3f] [%-10.3f]<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, x, <span class="pl-c1">2</span>.);
<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span><span class="pl-cce">\n</span><span class="pl-pds">"</span></span>);


cout &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>保留3位小数: <span class="pl-pds">"</span></span> 
        &lt;&lt; fixed &lt;&lt; setprecision(<span class="pl-c1">3</span>) &lt;&lt; x &lt;&lt; endl 
        &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>保留3位小数，宽度10且左对齐: [<span class="pl-pds">"</span></span> &lt;&lt; left
        &lt;&lt; setw(<span class="pl-c1">10</span>) &lt;&lt; setfill(<span class="pl-s"><span class="pl-pds">'</span> <span class="pl-pds">'</span></span>) &lt;&lt; x &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>] [<span class="pl-pds">"</span></span>
        &lt;&lt; setw(<span class="pl-c1">10</span>) &lt;&lt; setfill(<span class="pl-s"><span class="pl-pds">'</span>*<span class="pl-pds">'</span></span>) &lt;&lt; x &lt;&lt; <span class="pl-s"><span class="pl-pds">"</span>]<span class="pl-cce">\n</span><span class="pl-pds">"</span></span> 
        &lt;&lt; resetiosflags(ios::left);</pre></div>
<p>输出</p>
<pre><code>保留3位小数: 6.667
保留3位小数，宽度10且左对齐: [6.667     ] [2.000     ]

保留3位小数: 6.667
保留3位小数，宽度10且左对齐: [6.667     ] [6.667*****]
</code></pre>
<h2><a id="user-content-关于两种格式控制的评论" class="anchor" aria-hidden="true" href="#关于两种格式控制的评论"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>关于两种格式控制的评论</h2>
<p>翻译自 <a href="https://stackoverflow.com/questions/2872543/printf-vs-cout-in-c" rel="nofollow">https://stackoverflow.com/questions/2872543/printf-vs-cout-in-c</a></p>
<ol>
<li>可拓展性。 <code>std::cout</code> 易于重载，因此可以承接各种各样的对象。而 <code>printf</code> 一般只能承接基本类型。</li>
<li>直观性。 <code>printf</code> 相对而言字符串更紧凑，易于理解。而<code>std::cout</code> 的流控制语义非常复杂，且有滥用 流运算符 <code>&lt;&lt;</code> 的趋势，因此不易理解。</li>
<li>性能。 <code>printf</code> 的 IO 性能更好。 <code>std::cout</code> 往往需要设置如下命令来提高 IO 性能。</li>
</ol>
<div class="highlight highlight-source-c++"><pre><span class="pl-en">std::ios::sync_with_stdio</span>(<span class="pl-c1">false</span>);
std::cin.tie(<span class="pl-c1">0</span>);</pre></div>
<ol start="4">
<li>类型安全。<code>printf</code> 最为人诟病的是类型不安全。不过可以设置编译器提供编译期间的检查，并产生 Warning。</li>
</ol>
<div class="highlight highlight-source-c++"><pre>#<span class="pl-k">include</span> <span class="pl-s"><span class="pl-pds">&lt;</span>stdio.h<span class="pl-pds">&gt;</span></span>

<span class="pl-k">int</span> <span class="pl-en">main</span>(<span class="pl-k">void</span>) {
    <span class="pl-c1">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>String: %s<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, <span class="pl-c1">42</span>);
    <span class="pl-k">return</span> <span class="pl-c1">0</span>;
}
</pre></div>
<p>编译提醒</p>
<div class="highlight highlight-source-c++"><pre>safety.c:<span class="pl-c1">4</span>:<span class="pl-c1">28</span>: warning: format specifies type <span class="pl-s"><span class="pl-pds">'</span>char *<span class="pl-pds">'</span></span> but the argument has type <span class="pl-s"><span class="pl-pds">'</span>int<span class="pl-pds">'</span></span> [-Wformat]
    <span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>String: %s<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, <span class="pl-c1">42</span>);
                    ~~     ^~
                    %d
<span class="pl-c1">1</span> warning generated.</pre></div>
<h2><a id="user-content-printf-详解" class="anchor" aria-hidden="true" href="#printf-详解"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a><code>printf</code> 详解</h2>
<p>C++ 中 <code>printf()</code> 函数位于库文件 <code>&lt;cstdio&gt;</code> 或者 <code>&lt;stdio.h&gt;</code>，其功能为将格式化的数据打印到标准输出。</p>
<p>其调用格式为</p>
<pre><code>printf("&lt;格式化字符串&gt;", &lt;参量表&gt;);
</code></pre>
<h3><a id="user-content-函数原型" class="anchor" aria-hidden="true" href="#函数原型"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>函数原型</h3>
<div class="highlight highlight-source-c++"><pre><span class="pl-k">int</span> <span class="pl-en">printf</span> ( <span class="pl-k">const</span> <span class="pl-k">char</span> * format, ... );</pre></div>
<h3><a id="user-content-格式化字符串的参数" class="anchor" aria-hidden="true" href="#格式化字符串的参数"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>格式化字符串的参数</h3>
<ul>
<li>
<p><code>format</code> 这是字符串，包含了要被写入到标准输出 <code>stdout</code> 的文本。它可以包含嵌入的 <code>format</code> 标签， <code>format</code> 标签可被随后的附加参数中指定的值替换，并按需求进行格式化。 <code>format</code> 标签属性是</p>
<p><code>%[flags][width][.precision][length]specifier</code></p>
<p>具体讲解如下：</p>
</li>
</ul>
<table>
<thead>
<tr>
<th align="center"><code>specifier</code> (格式字符)</th>
<th align="left">意义</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center">d, i</td>
<td align="left">以十进制形式输出带符号整数(正数不输出符号)</td>
</tr>
<tr>
<td align="center">o</td>
<td align="left">以八进制形式输出无符号整数(不输出前缀0)</td>
</tr>
<tr>
<td align="center">x, X</td>
<td align="left">以十六进制形式输出无符号整数(不输出前缀Ox)</td>
</tr>
<tr>
<td align="center">u</td>
<td align="left">以十进制形式输出无符号整数</td>
</tr>
<tr>
<td align="center">f</td>
<td align="left">以小数形式输出单、双精度实数</td>
</tr>
<tr>
<td align="center">e, E</td>
<td align="left">以指数形式输出单、双精度实数</td>
</tr>
<tr>
<td align="center">g, G</td>
<td align="left">以%f或%e中较短的输出宽度输出单、双精度实数</td>
</tr>
<tr>
<td align="center">c</td>
<td align="left">输出单个字符</td>
</tr>
<tr>
<td align="center">s</td>
<td align="left">输出字符串</td>
</tr>
<tr>
<td align="center">p</td>
<td align="left">输出指针地址</td>
</tr>
<tr>
<td align="center">lu</td>
<td align="left">32位无符号整数</td>
</tr>
<tr>
<td align="center">llu</td>
<td align="left">64位无符号整数</td>
</tr>
</tbody>
</table>
<table>
<thead>
<tr>
<th align="center"><code>flags</code> (标识)</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center">-</td>
<td align="left">在给定的字段宽度内左对齐，默认是右对齐（参见 width 子说明符）。</td>
</tr>
<tr>
<td align="center">+</td>
<td align="left">强制在结果之前显示加号或减号（+ 或 -），即正数前面会显示 + 号。默认情况下，只有负数前面会显示一个 - 号。</td>
</tr>
<tr>
<td align="center">空格</td>
<td align="left">如果没有写入任何符号，则在该值前面插入一个空格。</td>
</tr>
<tr>
<td align="center">#</td>
<td align="left">与 o、x 或 X 说明符一起使用时，非零值前面会分别显示 0、0x 或 0X。 与 e、E 和 f 一起使用时，会强制输出包含一个小数点，即使后边没有数字时也会显示小数点。默认情况下，如果后边没有数字时候，不会显示显示小数点。 与 g 或 G 一起使用时，结果与使用 e 或 E 时相同，但是尾部的零不会被移除。</td>
</tr>
<tr>
<td align="center">0</td>
<td align="left">在指定填充 padding 的数字左边放置零（0），而不是空格（参见 width 子说明符）。</td>
</tr>
</tbody>
</table>
<table>
<thead>
<tr>
<th align="center"><code>width</code> (宽度)</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center">(number)</td>
<td align="left">要输出的字符的最小数目。如果输出的值短于该数，结果会用空格填充。如果输出的值长于该数，结果不会被截断。</td>
</tr>
<tr>
<td align="center">*</td>
<td align="left">宽度在 format 字符串中未指定，但是会作为附加整数值参数放置于要被格式化的参数之前。</td>
</tr>
</tbody>
</table>
<table>
<thead>
<tr>
<th align="center"><code>.precision</code> (精度)</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center">.number</td>
<td align="left">对于整数说明符（d、i、o、u、x、X）：precision 指定了要写入的数字的最小位数。如果写入的值短于该数，结果会用前导零来填充。如果写入的值长于该数，结果不会被截断。精度为 0 意味着不写入任何字符。 对于 e、E 和 f 说明符：要在小数点后输出的小数位数。 对于 g 和 G 说明符：要输出的最大有效位数。 对于 s: 要输出的最大字符数。默认情况下，所有字符都会被输出，直到遇到末尾的空字符。 对于 c 类型：没有任何影响。 当未指定任何精度时，默认为 1。如果指定时不带有一个显式值，则假定为 0。</td>
</tr>
<tr>
<td align="center">.*</td>
<td align="left">精度在 format 字符串中未指定，但是会作为附加整数值参数放置于要被格式化的参数之前。</td>
</tr>
</tbody>
</table>
<table>
<thead>
<tr>
<th align="center"><code>length</code> (长度)</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center">h</td>
<td align="left">参数被解释为短整型或无符号短整型（仅适用于整数说明符：i、d、o、u、x 和 X）。</td>
</tr>
<tr>
<td align="center">l</td>
<td align="left">参数被解释为长整型或无符号长整型，适用于整数说明符（i、d、o、u、x 和 X）及说明符 c（表示一个宽字符）和 s（表示宽字符字符串）。</td>
</tr>
<tr>
<td align="center">L</td>
<td align="left">参数被解释为长双精度型（仅适用于浮点数说明符：e、E、f、g 和 G）。</td>
</tr>
</tbody>
</table>
<h3><a id="user-content-例子" class="anchor" aria-hidden="true" href="#例子"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>例子</h3>
<div class="highlight highlight-source-c++"><pre><span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>指定宽度10且右对齐: [%10s] <span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>);
<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>指定宽度10且左对齐: [%-10s] <span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>Hello<span class="pl-pds">"</span></span>);
<span class="pl-en">printf</span>(<span class="pl-s"><span class="pl-pds">"</span>保留3位小数: %.3f %.3f<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>, <span class="pl-c1">2</span>. / <span class="pl-c1">3</span>, <span class="pl-c1">2</span>.);</pre></div>
<p>输出</p>
<pre><code>指定宽度10且右对齐: [     Hello]
指定宽度10且左对齐: [Hello     ]
保留3位小数: 0.667 2.000
</code></pre>
</article>
  </div>

    </div>

  


  <details class="details-reset details-overlay details-overlay-dark" id="jumpto-line-details-dialog">
    <summary data-hotkey="l" aria-label="Jump to line"></summary>
    <details-dialog class="Box Box--overlay d-flex flex-column anim-fade-in fast linejump" aria-label="Jump to line">
      <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="js-jump-to-line-form Box-body d-flex" action="" accept-charset="UTF-8" method="get">
        <input class="form-control flex-auto mr-3 linejump-input js-jump-to-line-field" type="text" placeholder="Jump to line&hellip;" aria-label="Jump to line" autofocus>
        <button type="submit" class="btn" data-close-dialog>Go</button>
</form>    </details-dialog>
  </details>




  </div>
</div>

    </main>
  </div>

  </div>

        
<div class="footer container-xl width-full p-responsive" role="contentinfo">
    <div class="position-relative d-flex flex-row-reverse flex-lg-row flex-wrap flex-lg-nowrap flex-justify-center flex-lg-justify-between pt-6 pb-2 mt-6 f6 text-gray border-top border-gray-light ">
      <ul class="list-style-none d-flex flex-wrap col-12 col-lg-5 flex-justify-center flex-lg-justify-between mb-2 mb-lg-0">
        <li class="mr-3 mr-lg-0">&copy; 2020 GitHub, Inc.</li>
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to terms, text:terms" href="https://github.com/site/terms">Terms</a></li>
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to privacy, text:privacy" href="https://github.com/site/privacy">Privacy</a></li>
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to security, text:security" href="https://github.com/security">Security</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://githubstatus.com/" data-ga-click="Footer, go to status, text:status">Status</a></li>
          <li><a data-ga-click="Footer, go to help, text:help" href="https://docs.github.com">Help</a></li>
      </ul>

      <a aria-label="Homepage" title="GitHub" class="footer-octicon d-none d-lg-block mx-lg-4" href="https://github.com">
        <svg height="24" class="octicon octicon-mark-github" viewBox="0 0 16 16" version="1.1" width="24" aria-hidden="true"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path></svg>
</a>
      <ul class="list-style-none d-flex flex-wrap col-12 col-lg-5 flex-justify-center flex-lg-justify-between mb-2 mb-lg-0">
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to contact, text:contact" href="https://github.com/contact">Contact GitHub</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://github.com/pricing" data-ga-click="Footer, go to Pricing, text:Pricing">Pricing</a></li>
        <li class="mr-3 mr-lg-0"><a href="https://docs.github.com" data-ga-click="Footer, go to api, text:api">API</a></li>
        <li class="mr-3 mr-lg-0"><a href="https://services.github.com" data-ga-click="Footer, go to training, text:training">Training</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://github.blog" data-ga-click="Footer, go to blog, text:blog">Blog</a></li>
          <li><a data-ga-click="Footer, go to about, text:about" href="https://github.com/about">About</a></li>
      </ul>
    </div>
  <div class="d-flex flex-justify-center pb-6">
    <span class="f6 text-gray-light"></span>
  </div>
</div>



  <div id="ajax-error-message" class="ajax-error-message flash flash-error">
    <svg class="octicon octicon-alert" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M8.22 1.754a.25.25 0 00-.44 0L1.698 13.132a.25.25 0 00.22.368h12.164a.25.25 0 00.22-.368L8.22 1.754zm-1.763-.707c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0114.082 15H1.918a1.75 1.75 0 01-1.543-2.575L6.457 1.047zM9 11a1 1 0 11-2 0 1 1 0 012 0zm-.25-5.25a.75.75 0 00-1.5 0v2.5a.75.75 0 001.5 0v-2.5z"></path></svg>
    <button type="button" class="flash-close js-ajax-error-dismiss" aria-label="Dismiss error">
      <svg class="octicon octicon-x" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M3.72 3.72a.75.75 0 011.06 0L8 6.94l3.22-3.22a.75.75 0 111.06 1.06L9.06 8l3.22 3.22a.75.75 0 11-1.06 1.06L8 9.06l-3.22 3.22a.75.75 0 01-1.06-1.06L6.94 8 3.72 4.78a.75.75 0 010-1.06z"></path></svg>
    </button>
    You can’t perform that action at this time.
  </div>


    <script crossorigin="anonymous" async="async" integrity="sha512-bn/3rKJzBl2H64K38R8KaVcT26vKK7BJQC59lwYc+9fjlHzmy0fwh+hzBtsgTdhIi13dxjzNKWhdSN8WTM9qUw==" type="application/javascript" id="js-conditional-compat" data-src="https://github.githubassets.com/assets/compat-bootstrap-6e7ff7ac.js"></script>
    <script crossorigin="anonymous" integrity="sha512-CxjaMepCmi+z0LTeztU2S8qGD25LyHD6j9t0RSPevy63trFWJVwUM6ipAVLgtpMBBgZ53wq8JPkSeQ6ruaZL2w==" type="application/javascript" src="https://github.githubassets.com/assets/environment-bootstrap-0b18da31.js"></script>
    <script crossorigin="anonymous" async="async" integrity="sha512-0AXkWwkiw45XIvngmWo/0uryDdhd0Hur2YAUCEdd5+gYDVQb4ymn5FQkIBpMa5uoQybM3qSRdA04eqo8A35B7Q==" type="application/javascript" src="https://github.githubassets.com/assets/vendor-d005e45b.js"></script>
    <script crossorigin="anonymous" async="async" integrity="sha512-MImAWI8TKrFFO937djwu2lEmJWi7eavNSWzFs0Kd/feV7W38estgTLCGahlhMtUu9MZ5LuWtQ46LM6qxHJqPQw==" type="application/javascript" src="https://github.githubassets.com/assets/frameworks-30898058.js"></script>
    
    <script crossorigin="anonymous" async="async" integrity="sha512-5hcZPkyv7o5YO8ckKMKsNWmOm8eVmyHkCL9XKfhdCiW3K8sROU4nyH5jPspTtg1xwgfHYvR7l5ZiG8kkq01+Hw==" type="application/javascript" src="https://github.githubassets.com/assets/behaviors-bootstrap-e617193e.js"></script>
    
      <script crossorigin="anonymous" async="async" integrity="sha512-WmLHdpvEzC/gyDbs4RKm2+pVCCIDmiJ4vPW5zdX6lQN1CxH/gYnRSi0gyMHMJv5Xv7zUbD6vOgwlAO6yNI87Vg==" type="application/javascript" data-module-id="./contributions-spider-graph.js" data-src="https://github.githubassets.com/assets/contributions-spider-graph-5a62c776.js"></script>
      <script crossorigin="anonymous" async="async" integrity="sha512-2tVomjR7M73FMhb8dUvdjjzAErhNyLB9tL++hwpJeElQv494sCpS8OnWZL981ktAg30aqIypXD6TJjdvxcPEWQ==" type="application/javascript" data-module-id="./drag-drop.js" data-src="https://github.githubassets.com/assets/drag-drop-dad5689a.js"></script>
      <script crossorigin="anonymous" async="async" integrity="sha512-6E3ph805JNUrG/ivkdXS6lJPW99Ze7JlLusPAp2t035OQd+7AjD4X6g5hioZwPU1yFxczoNKdEKytmWgLp7WYw==" type="application/javascript" data-module-id="./jump-to.js" data-src="https://github.githubassets.com/assets/jump-to-e84de987.js"></script>
      <script crossorigin="anonymous" async="async" integrity="sha512-O5MUDplY2zVCSB3Jq0MiMf/lhuo8NBywywSaMZnViWL4ynNrhfhtn1LtGMfqYvyPP3BlHsq3Qli2a1ei19IqsQ==" type="application/javascript" data-module-id="./manage-membership.js" data-src="https://github.githubassets.com/assets/manage-membership-bootstrap-3b93140e.js"></script>
      <script crossorigin="anonymous" async="async" integrity="sha512-e14YmKeE7DtBVONbVv52sO9Sp56BRExkstaqtgYIAu3xlMNtMEXI2//4NqDn+THjxv49R/cobZ7cv8KFF6mspw==" type="application/javascript" data-module-id="./profile-pins-element.js" data-src="https://github.githubassets.com/assets/profile-pins-element-7b5e1898.js"></script>
      <script crossorigin="anonymous" async="async" integrity="sha512-JXSmOrOQXof4xz7y+engxtqrugUopipC5LwEmsfxit4PlVe48UECBUCLuujjIADm1kjb2f/9/azX+qNspSy90w==" type="application/javascript" data-module-id="./randomColor.js" data-src="https://github.githubassets.com/assets/randomColor-2574a63a.js"></script>
      <script crossorigin="anonymous" async="async" integrity="sha512-FOUgzyCYz3T1et4Stcl3MeKUX3mZkQcsMsTQDgBj6/CtW3HrwyGMaCeXGyhSjTGibphNptgZKgDNkvL+O+2uYw==" type="application/javascript" data-module-id="./sortable-behavior.js" data-src="https://github.githubassets.com/assets/sortable-behavior-14e520cf.js"></script>
      <script crossorigin="anonymous" async="async" integrity="sha512-Sqqua2FOZToK8Mzg1e4jBubR6ZCFO0gL2JHjgpqafLawUXr69ffELu+IhApoX5uhWlxXxJ0ooE89ANBMtWiUNA==" type="application/javascript" data-module-id="./tweetsodium.js" data-src="https://github.githubassets.com/assets/tweetsodium-4aaaae6b.js"></script>
      <script crossorigin="anonymous" async="async" integrity="sha512-3Q6/aKl7PXjI+jB+sUpF8+h/c+m0WOOTiExsBCxtrmhCgQX5kVWx1SA7LuELWaK0EjS4SNffZcXJMbs0hbqx8w==" type="application/javascript" data-module-id="./user-status-submit.js" data-src="https://github.githubassets.com/assets/user-status-submit-dd0ebf68.js"></script>
    
    <script crossorigin="anonymous" async="async" integrity="sha512-/qScxtjexP2u3QkKCuwrz5nBriYatgocp4bz+lKaWT2CfpZjON9ZtcjoJi8gvOTrSiWP8tD2yoXZ82R5W2UssQ==" type="application/javascript" src="https://github.githubassets.com/assets/repositories-bootstrap-fea49cc6.js"></script>
<script crossorigin="anonymous" async="async" integrity="sha512-4uQvKBaDHwwOtxkHrpFSW7T3ag6D4e9kAykpUagCtVeN9lyhnicMf5ABWbS57QNmhtFayornB8HuUIs805G5tQ==" type="application/javascript" src="https://github.githubassets.com/assets/diffs-bootstrap-e2e42f28.js"></script>
<script crossorigin="anonymous" async="async" integrity="sha512-2iOlkD8iyiXXmuWQIJPgs5fKKEUgQT+StG9y7v8yXsBOeHM2lcM1xu7e4GldRoDt50fTc5tIIL/Zu76YIWog/w==" type="application/javascript" src="https://github.githubassets.com/assets/github-bootstrap-da23a590.js"></script>
  <div class="js-stale-session-flash flash flash-warn flash-banner" hidden
    >
    <svg class="octicon octicon-alert" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M8.22 1.754a.25.25 0 00-.44 0L1.698 13.132a.25.25 0 00.22.368h12.164a.25.25 0 00.22-.368L8.22 1.754zm-1.763-.707c.659-1.234 2.427-1.234 3.086 0l6.082 11.378A1.75 1.75 0 0114.082 15H1.918a1.75 1.75 0 01-1.543-2.575L6.457 1.047zM9 11a1 1 0 11-2 0 1 1 0 012 0zm-.25-5.25a.75.75 0 00-1.5 0v2.5a.75.75 0 001.5 0v-2.5z"></path></svg>
    <span class="js-stale-session-flash-signed-in" hidden>You signed in with another tab or window. <a href="">Reload</a> to refresh your session.</span>
    <span class="js-stale-session-flash-signed-out" hidden>You signed out in another tab or window. <a href="">Reload</a> to refresh your session.</span>
  </div>
  <template id="site-details-dialog">
  <details class="details-reset details-overlay details-overlay-dark lh-default text-gray-dark hx_rsm" open>
    <summary role="button" aria-label="Close dialog"></summary>
    <details-dialog class="Box Box--overlay d-flex flex-column anim-fade-in fast hx_rsm-dialog hx_rsm-modal">
      <button class="Box-btn-octicon m-0 btn-octicon position-absolute right-0 top-0" type="button" aria-label="Close dialog" data-close-dialog>
        <svg class="octicon octicon-x" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M3.72 3.72a.75.75 0 011.06 0L8 6.94l3.22-3.22a.75.75 0 111.06 1.06L9.06 8l3.22 3.22a.75.75 0 11-1.06 1.06L8 9.06l-3.22 3.22a.75.75 0 01-1.06-1.06L6.94 8 3.72 4.78a.75.75 0 010-1.06z"></path></svg>
      </button>
      <div class="octocat-spinner my-6 js-details-dialog-spinner"></div>
    </details-dialog>
  </details>
</template>

  <div class="Popover js-hovercard-content position-absolute" style="display: none; outline: none;" tabindex="0">
  <div class="Popover-message Popover-message--bottom-left Popover-message--large Box box-shadow-large" style="width:360px;">
  </div>
</div>


  </body>
</html>

