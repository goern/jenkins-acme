# jenkins-acme
Jenkins S2I repository for ACME Corp

This is a heavily updated Jenkins image, see plugins.txt.

Use `oc process -v=OAUTH_CLIENT_REDIRECT_URI=`oc get route jenkins --template='{{if .spec.tls }}https{{ else }}http{{ end }}://{{ .spec.host }}/securityRealm/finishLogin'` jenkins-oauth-template | oc create -f -`

And `oc get oauthclients jenkins-oauth --template='{{ .secret }}'` if you forgot the generated secret.
