#!groovy

@Library("Infrastructure") _


properties([
  parameters([
    choice(name: 'Deprecation Warning', choices: 'ignore-me-just-used-for-description', description: '''<h2>Deprecated</h2>

<p>Shuttering is now done via <a href="https://github.com/hmcts/azure-public-dns">azure-public-dns</a> for all new applications,</p>
<p>Applications will be removed from the below list as they are migrated across.</p>

<p>If you can\'t find an application in the list update it\'s shutter value to true in azure-public-dns.</p>
<p>See the full <a href="https://hmcts.github.io/ways-of-working/path-to-live/shutter.html">documentation</a>.</p>'''),
    choice(name: 'PRODUCT_NAME', choices: 'idam-web-admin-idam\nidam-web-public-idam', description: 'Product + app name, i.e. cmc-citizen-frontend'),
    choice(name: 'ENVIRONMENT', choices: 'aat\ndemo\nprod', description: 'Environment where code should be build and deployed'),
    choice(name: 'SUBSCRIPTION', choices: 'nonprod\nprod', description: 'Azure subscriptions available to build in'),
    choice(name: 'STATUS', choices: 'off\non', description: 'off = no shutter page, on = shuttered. Takes ~2 minutes to take affect because of DNS')
  ])
])

node {
 stage("Toggle Shutter"){
   shutter(params.PRODUCT_NAME, params.ENVIRONMENT , params.SUBSCRIPTION, params.STATUS)
 }
}
