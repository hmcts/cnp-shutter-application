#!groovy

@Library("Infrastructure") _


properties([
  parameters([
    choice(name: 'PRODUCT_NAME', choices: 'cmc-citizen-frontend\ncmc-legal-frontend\ndiv-pfe\nprobate-frontend', description: 'Product + app name, i.e. cmc-citizen-frontend'),
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

