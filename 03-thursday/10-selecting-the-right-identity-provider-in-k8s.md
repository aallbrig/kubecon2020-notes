## Meta
Sched URL(s): https://kccncna20.sched.com/event/ekA6/selecting-the-right-identity-provider-for-kubernetes-a-comparative-survey-cameron-seader-suse

Youtube URL(s):

## Selecting the Right Identity Provider for Kubernetes: A Comparative Survey - Cameron Seader, SUSE

### AuthN & AuthZ
Authentication == establish identity through trusted source.

Authorization == is an identity allowed to interact with a target resource?

### SAML vs OAuth vs OIDC

### Typical IdP architecture (for k8s)

### Do we still need LDAP in 2020?
Although it has been around for ages, it is stateful, no MFA, and it doesn't scale well.

### Outstanding crowd in the crowd
- Gluu
- OpenIAM

### Common markers of interest

| Marker | _ |
| Identity Federation | Linking of identities and attributes across IdPs |
| Open Source | |
| Protocol Support |
| MFA | |
| User Management | |
| Automated Client Registration | |
| Backend Support | |
| Language | |
| Developer Community | |
| Architecture | |
| Helm chart / easy k8s | |

### Comparison
IMO, openAMI looks great.
