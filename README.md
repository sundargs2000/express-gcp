# Express on Google App Engine

<p>
  <img src="https://symbols-electrical.getvecta.com/stencil_82/34_google-appengine-icon.e31a7499e4.svg" height="20">
  <b>A Stack</b> to develop, preview, and deploy an Express website to Google App Engine in seconds.
</p>

## Why should you use this stack?
Spin up your own ExpressJS website on Google App Engine in seconds.
The stack also sets up a CI/CD environment by taing care of the following things
1. Branch Naming convention - You can use any branch prefixed with "dev" as your development environment. 
2. Branch Protection Setting - Developers working on this branch can work freely and push changes without a PR and a code reviewer. This facilitates quick development. 
3. Enable Security alerts - A workflow will be setup for you to enable Dependabot alerts to detect vulnerabilities.
4. CodeQL Security Analysis - Discover vulnerabilities across a codebase with CodeQL, our industry-leading semantic code analysis engine

Note: Once you create a repo out of this stack, you can find your website deployed at TBF.

## What are the inputs to pass while setting up the stack?
-   `workload_identity_provider`: (Required) The full identifier of the Workload Identity
    Provider, including the project number, pool name, and provider name. If
    provided, this must be the full identifier which includes all parts:

    ```text
    projects/123456789/locations/global/workloadIdentityPools/my-pool/providers/my-provider
    ```

-   `service_account`: (Required) Email address or unique identifier of the Google Cloud
    service account for which to generate credentials. For example:

    ```text
    my-service-account@my-project.iam.gserviceaccount.com
    ```

-   `audience`: (Required) The value for the audience (`aud`) parameter in the
    generated GitHub Actions OIDC token. This value defaults to the value of
    `workload_identity_provider`, which is also the default value Google Cloud
    expects for the audience parameter on the token. We do not recommend
    changing this value.

For more info on getting these inputs look at the google [auth action](https://github.com/google-github-actions/auth/blob/main/README.md#inputs) which has in depth details about getting these inputs.
