:is-up-to-date: True

.. index:: Sidebar Configuration

.. _sidebar-configuration:

#####################
Sidebar Configuration
#####################

The sidebar configuration file configures the items available for interaction on the left side of Studio.  The Sidebar shows different projections of the content in addition to other tools to assist in content authoring.
To modify the sidebar configuration, click on |siteConfig| from the bottom of the *Sidebar*, then click on **Configuration** and select **Sidebar Configuration** from the dropdown list.

.. image:: /_static/images/site-admin/config-open-sidebar-config.png
    :alt: Configurations - Open Sidebar Configuration
    :width: 65 %
    :align: center

******
Sample
******

.. code-block:: xml
    :caption: {REPOSITORY_ROOT}/sites/SITENAME/config/studio/context-nav/sidebar.xml
    :linenos:

    <?xml version="1.0" encoding="UTF-8"?>
    <!-- sidebar.xml
    	This configuration file controls the SideBar in Crafter Studio. The SideBar is the left bar that shows
    	different projections of the content in addition to other tools to assist in content authoring.

        <contextNav>
          <modulehook>
    		<name>dashboard</name>
    		<params>
              <label>Dashboard</label>
    		  <path>/site-dashboard</path>
              <icon>  	               (optional icon customization - only one state (no tree link))
    		    <class>fa-cog</class>  (change default icon - using Font Awesome class)
                <styles> 	           (Change default icon styles - using css rules)
    		      <color>#409a00</color>
    			  <font-size>16px</font-size>
    		    </styles>
    		  </icon>
    		  <roles>
    			<role>admin</role>
    			<role>developer</role>
    		  </roles>
    		  <label>Site Config</label>
    		  <path>/site-config</path>
    		  <showRootItem>true</showRootItem>
    		  <onClick>preview</onClick>
    		</params>
          </modulehook>
    	</contextNav>
                
    	<contextNav>
          <modulehook>
              <name>wcm-root-folder</name>
              <showDivider>true</showDivider>
              <label>Pages</label>
              <path>/site/website</path>
    		  <module-icon-open>       (optional module-icon-open customization - state open)
                <class>fa-cog</class>
                <styles>
                    <color>#409a00</color>
                    <font-size>16px</font-size>
                </styles>
              </module-icon-open>
              <module-icon-closed>     (optional module-icon-closed customization - state close)
                <class>fa-cog</class>
                <styles>
                    <color>#409a00</color>
                    <font-size>16px</font-size>
                </styles>
              </module-icon-closed>
              <showRootItem>true</showRootItem>
              <onClick>preview</onClick>
    		</params>
          </modulehook>
    	</contextNav>

        Common module hooks include:
           <modulehook>
              <name>wcm-root-folder</name>           Type: Browsable content tree of descriptors and folders
              <showDivider>true</showDivider>        Display a visual divider after the folder (true/false)
              <params>
                 <label>Pages</label>                Label
                 <path>/site/website</path>          Path to root tree at. You mave multiple path elements
                 <showRootItem>true</showRootItem>   Display the root folder (true/false)
                 <onClick>preview</onClick>          Attempt to preview asset on click
                 <roles>...</roles>                  (optional roles list that has access to the menu item)
              </params>
           </modulehook>

           <modulehook>
              <name>wcm-asset-folder</name>          Type: Browsable content tree of files and folders
              <showDivider>true</showDivider>        Display a visual divider after the foler (true/false)
              <params>
                 <label>Static Assets</label>        Label
                 <path>/static-assets</path>         Path to root tree at. You mave multiple path elements
                 <showRootItem>true</showRootItem>   Display the root folder (true/false)
                 <onClick>preview</onClick>          Attempt to prview asset on click
                 <roles>...</roles>                  (optional roles list that has access to the menu item)
              </params>
           </modulehook>

          <modulehook>
            <name>dashboard</name>                   Type: Display a link to the Sites Dashboard
            <params>
              <label>Dashboard</label>               Label
              <path>/site-dashboard</path>           Relative link to Sites Dashboard
              <roles>...</roles>                     (optional roles list that has access to the menu item)
            </params>
          </modulehook>

          <modulehook>
            <name>site-config</name>                 Type: Display a link to the Site Config Panel
            <params>
              <label>Dashboard</label>               Label
              <path>/site-dashboard</path>           Relative link to Site Config Panel
              <roles>...</roles>                     (optional roles list that has access to the menu item)
            </params>
          </modulehook>
    -->
    <contextNav>
      <contexts>
    	<context>
          <groups>
    		<group>
    	  	  <menuItems>
    			<menuItem>
    		 	  <modulehooks>
    			  <!-- dashboard -->
    				<modulehook>
    				  <name>dashboard</name>
    				  <params>
    				    <label>Dashboard</label>
    					<path>/site-dashboard</path>
    				  </params>
    				</modulehook>

    			  <!-- Site IA PAGES -->
    			    <modulehook>
    				  <name>wcm-root-folder</name>
    				  <showDivider>true</showDivider>
    				  <params>
    					<label>Pages</label>
    					<path>/site/website</path>
    					<showRootItem>true</showRootItem>
    					<onClick>preview</onClick>
    				  </params>
    				</modulehook>

    			  <!-- COMPONENTS -->
    				<modulehook>
    				  <name>wcm-root-folder</name>
    				  <showDivider>true</showDivider>
    				  <params>
    					<label>Components</label>
    					<path>/site/components</path>
    					<showRootItem>true</showRootItem>
    				  </params>
    				</modulehook>

    				<modulehook>
    				  <name>wcm-assets-folder</name>
    				  <showDivider>true</showDivider>
    				  <params>
    				    <label>Static Assets</label>
    					<path>/static-assets</path>
    					<showRootItem>true</showRootItem>
    					<onClick>none</onClick>
    				  </params>
    				</modulehook>

    				<modulehook>
    				  <name>wcm-assets-folder</name>
    				  <showDivider>true</showDivider>
    				  <params>
    					<label>Templates</label>
    					<path>/templates</path>
    					<showRootItem>true</showRootItem>
    					<onClick>none</onClick>
    				  </params>
    				</modulehook>

    				<modulehook>
    				  <name>wcm-assets-folder</name>
    				  <showDivider>true</showDivider>
    				  <params>
    				    <label>Scripts</label>
    					<path>/scripts</path>
    					<showRootItem>true</showRootItem>
    					<onClick>none</onClick>
    				  </params>
    				</modulehook>

    				<modulehook>
    				  <name>site-config</name>
    				  <showDivider>true</showDivider>
    				  <params>
    				    <roles>
    					  <role>admin</role>
    					  <role>developer</role>
    					</roles>
    					<label>Site Config</label>
    					<path>/site-config</path>
    				  </params>
    				</modulehook>
    			  </modulehooks>

    			</menuItem>
    		  </menuItems>
    		</group>
    	  </groups>
    	</context>
      </contexts>
    </contextNav>
