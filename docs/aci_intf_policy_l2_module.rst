.. _aci_intf_policy_l2:


aci_intf_policy_l2 - Manage Layer 2 interface policies on Cisco ACI fabrics (l2:IfPol)
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.4


.. contents::
   :local:
   :depth: 2


Synopsis
--------

* Manage Layer 2 interface policies on Cisco ACI fabrics.
* More information from the internal APIC class *l2:IfPol* at https://developer.cisco.com/media/mim-ref/MO-l2IfPol.html.


Requirements (on host that executes module)
-------------------------------------------

  * ACI Fabric 1.0(3f)+


Options
-------

.. raw:: html

    <table border=1 cellpadding=4>

    <tr>
    <th class="head">parameter</th>
    <th class="head">required</th>
    <th class="head">default</th>
    <th class="head">choices</th>
    <th class="head">comments</th>
    </tr>

    <tr>
    <td>description<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td></td>
    <td></td>
    <td>
        <div>The description of the Layer 2 interface policy.</div>
        </br><div style="font-size: small;">aliases: descr</div>
    </td>
    </tr>

    <tr>
    <td>hostname<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td></td>
    <td>
        <div>IP Address or hostname of APIC resolvable by Ansible control host.</div>
        </br><div style="font-size: small;">aliases: host</div>
    </td>
    </tr>

    <tr>
    <td>l2_policy<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td></td>
    <td>
        <div>The name of the Layer 2 interface policy.</div>
        </br><div style="font-size: small;">aliases: name</div>
    </td>
    </tr>

    <tr>
    <td>password<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td></td>
    <td></td>
    <td>
        <div>The password to use for authentication.</div>
    </td>
    </tr>

    <tr>
    <td>qinq<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>disabled</td>
    <td><ul><li>core</li><li>disabled</li><li>edge</li></ul></td>
    <td>
        <div>Determines if QinQ is disabled or if the port should be considered a core or edge port.</div>
    </td>
    </tr>

    <tr>
    <td>state<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>present</td>
    <td><ul><li>absent</li><li>present</li><li>query</li></ul></td>
    <td>
        <div>Use <code>present</code> or <code>absent</code> for adding or removing.</div>
        <div>Use <code>query</code> for listing an object or multiple objects.</div>
    </td>
    </tr>

    <tr>
    <td>timeout<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>30</td>
    <td></td>
    <td>
        <div>The socket level timeout in seconds.</div>
    </td>
    </tr>

    <tr>
    <td>use_proxy<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>yes</td>
    <td><ul><li>yes</li><li>no</li></ul></td>
    <td>
        <div>If <code>no</code>, it will not use a proxy, even if one is defined in an environment variable on the target hosts.</div>
    </td>
    </tr>

    <tr>
    <td>use_ssl<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>yes</td>
    <td><ul><li>yes</li><li>no</li></ul></td>
    <td>
        <div>If <code>no</code>, an HTTP connection will be used instead of the default HTTPS connection.</div>
    </td>
    </tr>

    <tr>
    <td>username<br/><div style="font-size: small;"></div></td>
    <td>yes</td>
    <td>admin</td>
    <td></td>
    <td>
        <div>The username to use for authentication.</div>
        </br><div style="font-size: small;">aliases: user</div>
    </td>
    </tr>

    <tr>
    <td>validate_certs<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>yes</td>
    <td><ul><li>yes</li><li>no</li></ul></td>
    <td>
        <div>If <code>no</code>, SSL certificates will not be validated.</div>
        <div>This should only set to <code>no</code> used on personally controlled sites using self-signed certificates.</div>
    </td>
    </tr>

    <tr>
    <td>vepa<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>disabled</td>
    <td><ul><li>disabled</li><li>enabled</li></ul></td>
    <td>
        <div>Determines if Virtual Ethernet Port Aggregator is disabled or enabled.</div>
    </td>
    </tr>

    <tr>
    <td>vlan_scope<br/><div style="font-size: small;"></div></td>
    <td>no</td>
    <td>global</td>
    <td><ul><li>global</li><li>portlocal</li></ul></td>
    <td>
        <div>The scope of the VLAN.</div>
    </td>
    </tr>

    </table>
    </br>



Examples
--------

 ::

    
    - aci_intf_policy_l2:
        hostname: '{{ hostname }}'
        username: '{{ username }}'
        password: '{{ password }}'
        l2_policy: '{{ l2_policy }}'
        vlan_scope: '{{ vlan_policy }}'
        description: '{{ description }}'


Notes
-----

.. note::
    - By default, if an environment variable ``<protocol>_proxy`` is set on the target host, requests will be sent through that proxy. This behaviour can be overridden by setting a variable for this task (see `setting the environment <http://docs.ansible.com/playbooks_environment.html>`_), or by using the ``use_proxy`` option.
    - HTTP redirects can redirect from HTTP to HTTPS so you should be sure that your proxy environment for both protocols is correct.



Status
~~~~~~

This module is flagged as **preview** which means that it is not guaranteed to have a backwards compatible interface.

For help in developing on modules, should you be so inclined, please read :doc:`community`, :doc:`dev_guide/testing` and :doc:`dev_guide/developing_modules`.
