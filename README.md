# ansible-stig-automation-demo


### Manual process way
```
oscap xccdf eval --profile xccdf_org.ssgproject.content_profile_stig --results /tmp/oscap-report.xml /usr/share/xml/scap/ssg/content/ssg-rhel8-ds.xml

oscap xccdf generate fix --fix-type ansible --result-id "" --output stig-playbook-result.yml /tmp/oscap-report.xml
```
