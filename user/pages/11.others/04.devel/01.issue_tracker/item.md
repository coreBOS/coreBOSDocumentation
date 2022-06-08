---
title: 'coreBOS Issue Tracker Documentation'
metadata:
    description: 'coreBOS Issue Tracker Documentation'
    author: 'Joe Bordes'
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
taxonomy:
    category:
        - documentation
    tag:
        - issue
---
---
[Access coreBOS Issue Tracker](http://corebos.tsolucio.com/development)

## coreBOS Family Projects
- [coreBOS](http://localhost/coreBOSDocumentation/others/devel/issue_tracker/start)
- [coreBOS Documentation](http://localhost/coreBOSDocumentation/others/devel/issue_tracker/corebosdocs_start)
- [coreBOS Mail](http://localhost/coreBOSDocumentation/others/devel/issue_tracker/corebosmail_start)
- [coreBOS Customer Portal](http://localhost/coreBOSDocumentation/others/devel/issue_tracker/coreboscp_start)
- [coreBOS Business Intelligence](http://localhost/coreBOSDocumentation/others/devel/issue_tracker/corebosbi_start)
- [coreBOS Apps](http://localhost/coreBOSDocumentation/others/devel/issue_tracker/corebosapps_start)

## Issue Tracker Integration with Wiki

[Integration With dokuwiki](https://www.mantisbt.org/wiki/doku.php/mantisbt:issue:7075:integration_with_dokuwiki)

This part of the documentation is an integration between [mantisBT](https://mantisbt.org/) (our issue tracking software) and [dokuwiki](https://www.dokuwiki.org/dokuwiki) (our documentation software).

This integration flows in both directions.

From the issue tracker we can find two wiki links:

- the top menu wiki link will direct us to this page if “All Projects” are selected or directly to the selected project's page if one is selected.
- the wiki link on the top of each issue will take us directly to a specific wiki page where that issue can be explained.

From the wiki we can reference any issue with this syntax:
```
~~issue:nnn~~
```

where nnn is the number of the ticket in [mantisBT](https://mantisbt.org/)

## Issue Tracker Integration with GITHUB

[https://github.com/mantisbt-plugins/source-integration](https://github.com/mantisbt-plugins/source-integration)

[http://noswap.com/projects/source-integration](https://noswap.com/projects/source-integration)

## Issue Tracker Integration with Subversion

Create repository entries using WebSVN if you want the compare, diff and files links to work.

[http://noswap.com/blog/integrating-git-svn-with-mantisbt](http://noswap.com/blog/integrating-git-svn-with-mantisbt)

I had to also add this patch:

```
Index: plugins/SourceWebSVN/SourceWebSVN.php
===================================================================
--- plugins/SourceWebSVN/SourceWebSVN.php	(revisión: 3663)
+++ plugins/SourceWebSVN/SourceWebSVN.php	(copia de trabajo)
@@ -95,7 +95,7 @@
 			$t_url = $this->get_websvn_url( $p_repo );
 
 			if( !is_blank( $p_op ) ) {
-				$t_url .= "$p_op.php";
+				$t_url .= "$t_name/$p_op.php";
 			}
 
 			if( is_blank( $p_file ) ) {
@@ -107,7 +107,8 @@
 				$p_opts['path'] = $t_path;
 			}
 
-			$p_opts['repname'] = $t_name;
+			//$p_opts['repname'] = $t_name;
+			$p_opts['repname'] = $this->get_websvn_path( $p_repo );
 		}
 
 		return $t_url . '?' . http_build_query( $p_opts );
@@ -127,7 +128,8 @@
 
 	public function url_changeset( $p_repo, $p_changeset ) {
 		$t_rev = $p_changeset->revision;
-		$t_path = $this->get_websvn_path( $p_repo );
+		//$t_path = $this->get_websvn_path( $p_repo );
+		$t_path = '/'.$this->$p_repo->info['trunk_path'];
 		$t_opts = array();
 		$t_opts['compare[0]'] = $t_path . '@' . ($t_rev - 1);
 		$t_opts['compare[1]'] = $t_path . '@' . $t_rev;
Index: plugins/SourceSVN/SourceSVN.php
===================================================================
--- plugins/SourceSVN/SourceSVN.php	(revisión: 3663)
+++ plugins/SourceSVN/SourceSVN.php	(copia de trabajo)
@@ -78,7 +78,7 @@
 </tr>
 <tr <?php echo helper_alternate_class() ?>>
 <td class="category"><?php echo lang_get( 'plugin_SourceSVN_svn_password' ) ?></td>
-<td><input name="svn_password" maxlength="250" size="40" value="<?php echo string_attribute( $t_svn_password ) ?>"/></td>
+<td><input name="svn_password" type="password" maxlength="250" size="40" value="<?php echo string_attribute( $t_svn_password ) ?>"/></td>
 </tr>
 <tr <?php echo helper_alternate_class() ?>>
 <td class="category"><?php echo lang_get( 'plugin_SourceSVN_standard_repo' ) ?></td>
```