# selfhosted-authentication-table
List of SelfHosted apps, with information about their support for OpenID / SAML / LDAP / Proxy Auth

✔️ - Supported - all functionality works including mobile apps (if any)  
😔 - Supported, but breaks some features, mobile apps, users have to still be added manually or not maintained  
❌ - Unsupported  
❔ - Not known yet, to be added  

Proxy Auth theoretically works on all of them, but it will break functionality, display double logins etc.   
So only those explicitly working great with it will be marked as such. Otherwise it will be unsupported.  

| **Project**                                                                     | **OpenID** | **LDAP** | **Proxy Auth** | **Additional Info**                                                                                                                                                                                                                                                                                                    |   |
|---------------------------------------------------------------------------------|------------|----------|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|
| [Apache Guacamole](https://guacamole.apache.org/)                               | ✔️          | ✔️        | ✔️              | possible issues with openid accounts not getting created in guacamole automatically                                                                                                                                                                                                                                    |   |
| [audiobookshelf](https://www.audiobookshelf.org/)                               | ✔️          | ❌        | ❌              |  OpenID Connect support as of [Version 2.6.0](https://github.com/advplyr/audiobookshelf/releases/tag/v2.6.0)  [Documentation](https://github.com/adepssimius/audiobookshelf-web/blob/master/content/guides/11.sso_configuration.md)                                                              |   |
| [blink](https://github.com/JaneJeon/blink)                                      | ✔️          | ❌        | ❌              |                                                                                                                                                                                                                                                                                                                        |   |
| [Bookstack](https://www.bookstackapp.com/)                                      | ✔️          | ✔️        | ❌              | [documentation](https://www.bookstackapp.com/docs/admin/) -> `Authentication`                                                                                                                                                                                                                                          |   |
| [Calibre-Web](https://github.com/janeczku/calibre-web)                          | ❌          | ✔️        | 😔              | [LDAP documentation](https://github.com/janeczku/calibre-web/wiki/LDAP-Login), proxy auth seems to have issues with OPDS feed, OpenID supports only GitHub and Google OAuth, but generic is [being worked on](https://github.com/janeczku/calibre-web/pull/2211)                                                       |   |
| [changedetection](https://github.com/dgtlmoon/changedetection.io)               | ❌          | ❌        | ✔️              | No multi-user support, but it doesn't have that with default auth either                                                                                                                                                                                                                                               |   |
| [docker-mailserver](https://docker-mailserver.github.io/docker-mailserver/edge) | ❌          | 😔        | ❌              | LDAP supported, but unmaintained. OpenID [being worked on](https://github.com/docker-mailserver/docker-mailserver/issues/2713), but I wouldn't count on that as mail client support for xoauth2 is not good                                                                                                            |   |
| [Gitea](https://gitea.io/en-us/)                                                | ✔️          | ✔️        | ✔️              |                                                                                                                                                                                                                                                                                                                        |   |
| [GitLab](https://gitlab.com)                                                    | ✔️          | ✔️        | ❌              | [OpenID documentation](https://docs.gitlab.com/ee/administration/auth/oidc.html), [LDAP documentation](https://docs.gitlab.com/ee/administration/auth/ldap/)                                                                                                                                                           |   |
| [gokapi](https://github.com/Forceu/Gokapi)                                      | ✔️          | ❌        | ✔️              | [documentation](https://gokapi.readthedocs.io/en/latest/setup.html#authentication)                                                                                                                                                                                                                                     |   |
| [hedgedoc](https://hedgedoc.org)                                                | ✔️          | ✔️        | ❌              |                                                                                                                                                                                                                                                                                                                        |   |
| [Home Assistant](https://www.home-assistant.io)                                 | ❌          | 😔        | 😔              | [hass-proxy-auth](https://github.com/BeryJu/hass-auth-header) for proxy auth, but for some people it breaks mobile app, [hacky scripts](https://gist.github.com/rechner/57c123d243b8adb83ccb1dc94c80847f) for LDAP. [More Info](https://www.home-assistant.io/docs/authentication/providers/)                          |   |
| [Immich](https://immich.app/)                                         | ✔️          | ❌        | ❌              | [OIDC](https://documentation.immich.app/docs/administration/oauth) is supported natively.                           |   |
| [Jellyfin](https://jellyfin.org/)                                               | 😔          | ✔️        | ❌              | [LDAP plugin](https://github.com/jellyfin/jellyfin-plugin-ldapauth), [OpenID plugin](https://github.com/9p4/jellyfin-plugin-sso) breaks apps, [might be solved in the future](https://github.com/jellyfin/jellyfin-meta/issues/28)                                                                                     |   |
| [Linkding](https://github.com/sissbruecker/linkding)                                         | ❌          | ❌        | ✔️              | [ProxyAuth](https://github.com/sissbruecker/linkding/blob/master/docs/Options.md#ld_enable_auth_proxy) is supported.  
| [mailcow](https://mailcow.email/)                                               | ❌          | 😔        | ❌              | [hacky ldapsync script](https://github.com/Programmierus/ldap-mailcow), [issue about auth](https://github.com/mailcow/mailcow-dockerized/issues/2316)                                                                                                                                                                  |   |
| [mailu](https://mailu.io)                                                       | ❌          | ❌        | ❌              |                                                                                                                                                                                                                                                                                                                        |   |
| [matrix dendrite](https://github.com/matrix-org/dendrite)                       | ❌          | ❌        | ❌              | Some work on SSO in [this PR](https://github.com/matrix-org/dendrite/pull/2492), some work on LDAP [here](https://github.com/matrix-org/dendrite/pull/1877) but abandoned                                                                                                                                              |   |
| [matrix synapse](https://matrix.org/docs/projects/server/synapse)               | ✔️          | ✔️        | ❌              | LDAP Provided by additional module; openid supported natively                                                                                                                                                                                                                                                          |   |
| [Navidrome](https://navidrome.org)                                              | ❌         | ❌       | 😔              | Proxy auth works but requires you to previously create the users and [add some headers](https://www.navidrome.org/docs/usage/security/#reverse-proxy-authentication). [LDAP](https://github.com/navidrome/navidrome/issues/141) and [OpenID/OIDC](https://github.com/navidrome/navidrome/issues/858) are planned but not a priority.
| [NextCloud](https://nextcloud.com)                                              | ✔️          | ✔️        | ❌              | Install OpenID or LDAP plugin from interface to enable support                                                                                                                                                                                                                                                         |   |
| [Paperless-NGX](https://github.com/paperless-ngx/paperless-ngx)                 | ❌          | ❌        | 😔              | Proxy Auth [possible](https://goauthentik.io/integrations/services/paperless-ng) but doesn't autocreate users, [Issue about User Management](https://github.com/paperless-ngx/paperless-ngx/discussions/625), [possible hacky workaround for OpenID?](https://ciphermenial.github.io/posts/adding-oauth-to-paperless/) |   |
| [pihole](https://pi-hole.net)                                                   | ❌          | ❌        | ✔️              | Remove local auth with `pihole -a -p`, then enter for no password. No multi-user support, but it doesn't have that with default auth either                                                                                                                                                                            |   |
| [Portainer](https://www.portainer.io/)                                          | ✔️          | ✔️        | ❌              | [Documentation](https://docs.portainer.io/admin/settings/authentication/oauth)                                                                                                                                                                                                                                         |   |
| [Proxmox](https://www.proxmox.com/en/)                                          | ✔️          | ✔️        | ❌              | OpenID and LDAP both fully supported. Documentation [here](https://pve.proxmox.com/wiki/User_Management)                                                                                                                                                                                                               |   |
| [Radarr](https://radarr.video/)                                                 | ❌          | ❌        | ✔️              | Can follow the guide for Sonarr                                                                                                                                                                                                                                                                                        |   |
| [Sonarr](https://sonarr.tv/)                                                    | ❌          | ❌        | ✔️              | [Docs](https://goauthentik.io/integrations/services/sonarr/)                                                                                                                                                                                                                                                           |   |
| [Uptime Kuma](https://uptime.kuma.pet)                                          | ❌          | ❌        | ✔️              | `Settings` > `Advanced` > `Disable Auth` to avoid double login                                                                                                                                                                                                                                                         |   |
| [vaultwarden](https://github.com/dani-garcia/vaultwarden)                       | ❌          | ✔️        | ❌              | [Invitation-Based LDAP](https://github.com/dani-garcia/vaultwarden/wiki/Syncing-users-from-LDAP), OpenID being worked on in [#2449](https://github.com/dani-garcia/vaultwarden/pull/2449)                                                                                                                              |   |
| [wg-portal](https://github.com/h44z/wg-portal)                                  | ❌          | ✔️        | ❌              |                                                                                                                                                                                                                                                                                                                        |   |
| [wg-ui](https://github.com/EmbarkStudios/wg-ui)                                 | ❌          | ❌        | ✔️              | via `--auth-user-header=HEADER` option                                                                                                                                                                                                                                                                                 |   |
| [WikiJS](https://js.wiki)                                 | ❌          | ✔️        |      ❌         | [LDAP](https://docs.requarks.io/auth/ldap) works natively. Supports SAML via [Passport](https://github.com/node-saml/passport-saml), though not officially supported.