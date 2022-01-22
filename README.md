Ansible Inventory Report
============================================

An HTML based report to target Cisco based network devices and facts, using the `cisco.ios.ios` collection.  HTML markup is generated from a series of `Jinja2` templates, and styled with the `UIkit`, and `FontAwesome` CSS frameworks, via their `CDN` links for portability.

>Shoutout to the original author, Red Hat, and the Ansible community for inspiration and guidance.

Notes
============================================
- Please see the role's `README.md` file for more information about its use, and the `sample_report_output.png` for a peek at the output.
- This role is designed to be a starting point for building your own inventory report.  Feel free to fork and make your own changes.
- I am not a professional front-end developer, but I have attempted to provide clean HTML markup based on the framework documentation.