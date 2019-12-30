# ansible-pwm

Install PWM

# Requirements

Java JDK 11 or later
Apache Tomcat 8.5 or later


# Role Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `pwm_path_config`| Path of configuration files    | `/media/pwm` |
| `pwm_name_war`| File name war | `pwm-2.0.0-SNAPSHOT.war` |
| `pwm_domains`| Depending on the email domain, the user is added to certain groups | `null` |
| `pwm_services`| Add all new users to groups of this variable | `null` |
| `pwm_template_ldap`| LDAP Vendor Default Settings | `OPEN_LDAP` |
| `pwm_template_storage`| Storage default settings | `LDAP` |
| `pwm_ldap_profile_list`| LDAP profile list | `default` |
| `pwm_ldap_serverurls`| LDAP url | `ldap://server.net:389` |
| `pwm_ldap_proxy_username`| Specify the LDAP Proxy User PWM uses to access the LDAP directory | `cn=admin,dc=server,dc=net` |
| `pwm_ldap_proxy_password`| Specify the password of the LDAP Proxy User | `9.0.1` |
| `pwm_ldap_rootcontexts`| Specify the base context(s) to search for user names during authentication and other operations | `ou=gente,dc=server,dc=net` |
| `pwm_ldap_testuser_username`| Specify the fully qualified DN of an LDAP test user that PWM uses to test functionality and for access to the LDAP directory | `cn=uprueba,ou=gente,dc=server,dc=net` |
| `pwm_pwmadmin_querymatch`| Administrator Permission | `!unsafe '{"ldapProfileID":"default","ldapBase":"cn=admin,ou=groups,dc=server,dc=net","type":"ldapGroup"}'` |
| `pwm_db_classname`| if you use databases (name) | `null` |
| `pwm_db_url`| if you use databases (url) | `null` |
| `pwm_db_username`| if you use databases (username) | `null` |
| `pwm_db_password`| if you use databases (password) | `null` |
| `pwm_publishstats_enable`| Enable Anonymous Statistics Publishing | `false` |
| `pwm_selfurl`| Site URL | `http://serverPWM/pwm` |
| `pwm_display_showdetailederrors`| Show Detailed Error Messages | `true` |
| `pwm_securitykey`| Security key (SHA-1) | `null` |
| `pwm_password_policy_source`| Password Policy Source | `PWM` |
| `pwm_interface_theme`| Theme | `autumn` |
| `pwm_forgottenusername_enable`| Enable Forgotten User Name | `true` |
| `pwm_recovery_searchfilter`| Forgotten Password User Search Filter | `!unsafe '(&amp;(objectClass=person)(cn=%cn%))'` |
| `pwm_homeurl`| Home URL | `null` |
| `pwm_introurl`| Intro URL | `/public/` |
| `pwm_guest_enable`| Enable Guest Registration | `true` |
| `pwm_guest_createcontext`| Creation Context | `ou=gente` |
| `pwm_newuser_enable`| Enable New User Registration | `true` |
| `pwm_recovery_querymatch`| Forgotten Password Profile Match | `view file default` |
| `pwm_ldap_guid_autoaddvalue`| Auto Add GUID Value | `true` |
| `pwm_newuser_passwordpolicy_user`| Password Policy Template | `cn=admin,dc=server,dc=net` |
| `pwm_newuser_form`| New User Form | `view file default` |
| `pwm_newuser_createcontext`| Creation Context | `ou=gente,dc=server,dc=net` |
| `pwm_challenge_requiredattributes`| Required LDAP Attributes | `view file default` |
| `pwm_newuser_username_definition`| If you leave this field blank, the system does not generate a random user name or entry ID | `undefined` |
| `pwm_challenge_policy_queryMatch`| Specify an LDAP filter to search for users that have the permissions to set up Challenge/Responses. | `undefined` |
| `pwm_external_webservices_enable`| Enable REST Web Server | `true` |
| `pwm_webservices_public_enable`| Public REST Web Services | `ForgottenPassword` |
| `pwm_webservices_queryMatch`| Web Services LDAP Authentication Permissions | `undefined` |
| `pwm_webservices_thirdParty_queryMatch`| Web Services LDAP Third Party Permissions | `undefined` |
| `pwm_webservices_enablereadanswers`| Allow Challenge REST Service to Read Answers | `true` |
| `pwm_webservices_userattributes`| Web Service Non-LDAP Users and Passwords | `undefined` |
| `pwm_forcebasicauth`| Force Basic Authentication | `false` |
| `pwm_display_masktokenfields`| Enable this option to mask token input fields with standard "password" masking | `undefined` |
| `pwm_ldap_user_appdata_attribute`| Application Data Attribute | `pwmData` |
| `pwm_response_hashmethod`| Responses Storage Hashing Method | `SHA1_SALT` |
| `pwm_recovery_action`| Forgotten Password Recovery Mode | `undefined` |
| `pwm_activateuser_allowunlock`| Unlock User During Activation | `undefined` |
| `pwm_helpdesk_enable`| Enable Help Desk Module | `true` |
| `pwm_recovery_allowwhenlocked`| Allow Forgotten Password when Locked | `true` |
| `pwm_ldap_ad_proxyforgotten`| Use Proxy When Password Forgotten | `false` |
| `pwm_ldap_ad_allowauth_expired`| Allow Authentication When Password Expired | `undefined` |
| `pwm_password_allowchange_querymatch`| Change Password Permission | `!unsafe '{"ldapProfileID":"all","ldapQuery":"(objectClass=person)","type":"ldapQuery"}'` |
| `pwm_helpdesk_verificationmethods`| Verification Methods | `view file default` |
| `pwm_ldap_ad_enforcepwhistoryonset`| Enforce Password Policy During Forgotten Password | `undefined` |
| `pwm_ldap_ad_allowauth_requirenewpassword`| Allow Authentication When "Must Change Password On Next Login" Is Set | `false` |
| `pwm_guest_admingroup`| Guest Admin Permission | `undefined` |
| `pwm_activateuser_token_sendmethod`| Token Send Method | `EMAILONLY` |
| `pwm_activateuser_enable`| Enable User Activation | `false` |
| `pwm_display_newuser_agreement`| New User Agreement Message | `Terms and conditions of use` |
| `pwm_email_smtp_address`| SMTP Server Address | `localhost` |
| `pwm_email_newuser`| New User Email | `view file default` |
| `pwm_email_newuser_token`| New User Verification Email | `view file default` |
| `pwm_email_helpdesk_token`| Help Desk Verification Email | `view file default` |
| `pwm_email_guest`| Guest Registration Email | `view file default` |
| `pwm_newuser_writeattributes`| New User Actions | `view file default` |
| `pwm_webservice_userattributes`| Web Service User Attributes | `undefined` |
| `pwm_helpdesk_token_sendmethod`| Token Send Method | `EMAILONLY` |
| `pwm_challenge_minrandomssetup`| Minimum Random Challenges Required During Setup | `2` |
| `pwm_challenge_helpdesk_minrandomssetup`| Minimum Help Desk Random Challenges Required During Setup | `4` |
| `pwm_email_smtp_type`| SMTP Connection Type | `SMTP` |
| `pwm_email_default_fromaddress`| Default From Address | `admin@serverPWM` |
| `pwm_ldap_addobjectclasses`| Auto Add Object Classes | `pwmUser` |
| `pwm_email_changepassword`| Change Password Email | `view file default` |
| `pwm_email_changepassword_helpdesk`| Help Desk Change Password Email | `view file default` |
| `pwm_email_usermailattribute2`| Secondary User Email Attribute | `undefined` |
| `pwm_ldap_defaultobjectclasses`| User Object Class | `inetOrgPerson` |
| `pwm_password_policy_minimumlength`| Password Policy Minimum Length | `8` |
| `pwm_password_policy_maximumalpha`| Password Policy Maximum Alphabetic | `0` |
| `pwm_password_policy_minimumalpha`| Password Policy Minimum Alphabetic | `4` |
| `pwm_password_policy_minimumnumeric`| Password Policy Minimum Numeric | `2` |
| `pwm_password_policy_maximumsequentialrepeat`| Password Policy Maximum Sequential Repeat | `3` |
| `pwm_password_policy_minimumlowercase`| Password Policy Minimum Lowercase| `0` |
| `pwm_password_policy_minimumuppercase`| Password Policy Minimum Uppercase| `1` |
| `pwm_password_policy_minimumunique`| Password Policy Minimum Unique Characters| `5` |
| `pwm_guest_writeattributes`| Guest Creation Actions | `undefined` |
| `pwm_captcha_recaptcha_privatekey`| reCAPTCHA Secret| `vault` |
| `pwm_captcha_recaptcha_publickey`| reCAPTCHA Public| `vault` |
| `pwm_captcha_recaptcha_mode`| reCAPTCHA Mode| `V3` |
| `pwm_captcha_protectedpages`| CAPTCHA Protected Pages | `view file default` |
| `pwm_email_challenge_token`| Forgotten Password Verification Email | `view file default` |
| `pwm_idletimeoutseconds`| Idle Timeout Seconds | `900` |
| `pwm_logouturl`| Logout URL | `http://serverPWM/pwm` |
| `pwm_configiseditable`| Edit mode| `true` |
| `pwm_configpasswordhash`| Password hash| `value` |


# Dependencies

Previously install 

	*	https://github.com/UdelaRInterior/ansible-role-certbot
	* 	https://github.com/UdelaRInterior/ansible-reverse-proxy
	*	https://github.com/UdelaRInterior/oracle-java
	*	https://github.com/UdelaRInterior/ansible-role-tomcat

# Example Playbook

    - hosts: all
      roles:
        - { role: ansible-pwm }

# License

GPLv2

Author Information
------------------

https://github.com/UdelaRInterior/ansible-pwm
