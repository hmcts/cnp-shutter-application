#!groovy

@Library("Infrastructure") _


properties([
  parameters([
    choice(name: '_DEPRECATION_', choices: 'DEPRECATION', description: 'This JOB will soon be _DEPRECATED_ once all the frontend applications will be migrated to Azure Kubernetes Service.'),
    choice(name: 'PRODUCT_NAME', choices: 'cmc-citizen-frontend\ncmc-legal-frontend\nprobate-frontend\nprobate-caveats-fe\nccd-api-gateway-web\nccd-case-management-web\nfees-register-api\nfees-register-frontend\nsscs-tribunals-frontend\nsscs-tya-frontend\njui-webapp\nbar-web\nidam-web-admin-idam\nidam-web-public-idam\nsscs-cor-frontend\njui-webapp-web\nccpay-bubble-frontend\nxui-ao-webapp\nxui-mo-webapp\nxui-webapp', description: 'Product + app name, i.e. cmc-citizen-frontend'),
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

