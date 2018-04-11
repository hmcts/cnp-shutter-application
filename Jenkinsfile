#!groovy

@Library("Infrastructure") _


properties([
  parameters([
    string(name: 'PRODUCT_NAME', choices: 'cmc-citizen-frontend\ncmc-legal-frontend', description: 'Product + app name, i.e. cmc-citizen-frontend'),
    string(name: 'ENVIRONMENT', choices: 'aat\ndemo\nprod', description: 'Environment where code should be build and deployed'),
    choice(name: 'SUBSCRIPTION', choices: 'nonprod\nprod', description: 'Azure subscriptions available to build in'),
    choice(name: 'STATUS', choices: 'off\non', description: 'Toggle shutter page')
  ])
])

node {
 stage("Toggle Shutter"){
     shutter(params.PRODUCT_NAME, params.ENVIRONMENT , params.SUBSCRIPTION, params.STATUS)
 }
}

