project = memdevops
AND issuetype = "Trouble Report"
AND labels = IDTrouble
AND (
component in (
addressbook, addresssearch, "myr ap", "myr jp", profile
)
OR text ~ Addressbook
OR text ~ MyR
OR text ~ Addressearch
)
OR
project = midp AND issuetype = "Trouble Report"
OR
project = MIT AND issuetype = "story"
AND (
cf[13419] = MyRJP
OR cf[13419] = MyRAP
OR cf[13419] = ABAS
)
ORDER BY created DESC, key ASC
