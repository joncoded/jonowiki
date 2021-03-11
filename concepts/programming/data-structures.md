# Data structures

We can organize data in many different ways, each of which comprises a **data structure...** 

...and it really all comes down to what we need to do with the data: 

* Sorting?
* Searching?
* Retrieving?
* Frequent insertion and/or update?
* Relationship \(association\) modelling?

Below are some most commonly used **abstract data types:**

### **Tabular structures**

Data in tabular structures are organized in cells called **elements**: 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Key feature(s)</th>
      <th style="text-align:left">Applications</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Array</b>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Easy retrieval (accessibility)</li>
          <li>Difficult to insert data randomly (integrity)</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Spreadsheets</li>
          <li>Unordered lists</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Queue</b>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Retrieve only the oldest element to ensure old data becomes discarded
            as soon as possible (freshness)</li>
        </ul>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Login systems</li>
          <li>Live ticket ordering systems</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Hashtable </b>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Easy retrieval (accessibility)</li>
          <li>Handles large amounts of data (robustness)</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Databases</li>
          <li>Directiories with &quot;lookup&quot; functionality</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### Nodular structures

Data in nodular structures are organized into **nodes** that can connect through **edges** via referencing-based systems: 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Key features</th>
      <th style="text-align:left">Applications</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Single linked list</b>
        </p>
        <p></p>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Easy insertion (flexibility)</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Decentralized networks where nodes only connect to 0-2 other nodes</li>
          <li>Flight itinerary with connecting flights</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Double linked list</b>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Easy insertion (flexibility)</li>
          <li>&quot;Previous node&quot; and &quot;next node&quot;</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Previous/next webpage navigation</li>
          <li>Transit system representation</li>
          <li>Browser history</li>
          <li>Undo/redo history</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Tree </b>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Easy searching (accessibility)</li>
        </ul>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Hierarchical networks</li>
          <li>Search</li>
          <li>File systems</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Graph </b>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Conveys complex relationships in textual form</li>
        </ul>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Complex relationship diagrams</li>
          <li>Decentralized networks where nodes may connect to any number of nodes
            (social networks)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

Anyway, an _awareness_ of data structures builds an _awareness_ of **efficiency** when building any system \(not just websites\) ... when a system gets large, it then has the capability to **scale** \(i.e. handle that load!\)

Thus, organizing data using these theoretical concepts can go a long way!

