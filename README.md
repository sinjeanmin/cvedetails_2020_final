# cvedetails_2020_final
redoing cve_2020 repository

main idea how this repository works:
for every site scraped, we add an extra header column to the right that lists down the patch date if the patch exists.
if the scrape for a CVE has been attempted, dirty is set to 1.
at the end of all the scrapes, i.e. cve_2020_final_16.feather, i added an additional "earliest_patch" column which lists down the earliest patch date across the 15 sites that are scraped.

domains scraped (16):
['gentoo_opensuse_rustsec', #this is 3 sites
 'oracle',
 'apple',
 'ibm',
 'ubuntu',
 'debian',
 'android',
 'android_pixel',
 'bugzilla_redhat',
 'microsoft',
 'adobe',
 'cisco',
 'zerodayinitiative',
 'fedoraproject']


below states the progression from file _1 to _16:

-cve_2020_final_1.feather
Pius' edition, which includes "security.gentoo.org/glsa", "lists.opensuse.org/opensuse-security-announce/", "packetstormsecurity.com/files"
added patch date in new column 'gentoo_opensuse_rustsec'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_2.feather
removed duplicates
removed CVEs that are NOT CVE_2020
removed packetstormsecurity scrapes
renamed first_patch to gentoo_opensuse_rustsec
added dirtybit
renamed num_patches to has_patch

-cve_2020_final_3.feather
scraped oracle where domain = 'www.oracle.com/security-alerts/cpu'
added patch date in new column 'oracle'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_4.feather
scraped apple where domain = 'support.apple.com'
added patch date in new column 'apple'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_5.feather
scraped ibm where domain = 'ibm.com/support/pages/node/'
added patch date in new column 'ibm'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_6.feather
scraped ubuntu where domain = '/usn.ubuntu.com'
added patch date in new column 'ubuntu'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_7.feather
scraped debian where domain = 'www.debian.org'
added patch date in new column 'debian'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_8.feather
scraped android where domain = "source.android.com/security/bulletin/20"
added patch date in new column 'android'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_9.feather
scraped android_pixelwhere domain = "source.android.com/security/bulletin/pixel/"
added patch date in new column 'android_pixel'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_10.feather
scraped bugzilla_redhat where domain = 'bugzilla.redhat.com/show_bug'
added patch date in new column 'bugzilla_redhat '
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_11.feather
merged Pius' microsoft where domain = "portal.msrc.microsoft.com/en-US/security-guidance/advisory/"
added patch date in new column 'microsoft'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_12.feather
merged adobe where domain = "helpx.adobe.com/security/products/"
added patch date in new column 'adobe '
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_13.feather
merged cisco where domain = "tools.cisco.com/security/center/content/CiscoSecurityAdvisory/cisco-sa-"
added patch date in new column 'cisco'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_14.feather
merged zerodayinitiative where domain = "zerodayinitiative.com/advisories/"
added patch date in new column 'zerodayinitiative'
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_15.feather
merged fedoraproject where domain = 'lists.fedoraproject.org/archives/list/'
added patch date in new column 'fedoraproject '
updated dirtybit for all scrape attempts on above domain

-cve_2020_final_16.feather
Changing has_patch to 1 if each domain has a patch
Added last column 'earliest_patch' and compared across all domains to get earliest patch date