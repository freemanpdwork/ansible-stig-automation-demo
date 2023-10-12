# ansible-stig-automation-demo

WIP

### Red Hat Official STIG Playbook example
```
# Import Ansible role
ansible-galaxy install RedHatOfficial.rhel8_stig --force

# Execute Anisble playbook
ansible-playbook -i hosts playbook.yml -u test --ask-become-pass

```
Note: the Ansible automaiton for this can be found here: https://github.com/RedHatOfficial/ansible-role-rhel8-stig


### OpenSCAP manual way
```
# system scan
oscap xccdf eval --profile xccdf_org.ssgproject.content_profile_stig --results /tmp/oscap-report.xml /usr/share/xml/scap/ssg/content/ssg-rhel8-ds.xml

# Ansible playbook generation
oscap xccdf generate fix --fix-type ansible --result-id "" --output stig-playbook-result.yml /tmp/oscap-report.xml
```
