# Efficiency \(with big-O notation\)

**Measuring efficiency** of algorithms: given an input size of n, how much time would it take to process the algorithm if it operates in \(constant, logarithmic, linear, quadratic, exponential and factorial\) time? 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Big-O notation</th>
      <th style="text-align:left">Time if n=10</th>
      <th style="text-align:left">Time if
        <br />n=100</th>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">O(1)</td>
      <td style="text-align:left">1</td>
      <td style="text-align:left">1</td>
      <td style="text-align:left"><b>constant</b>
      </td>
      <td style="text-align:left">instant hashtable lookup</td>
    </tr>
    <tr>
      <td style="text-align:left">O(log n)</td>
      <td style="text-align:left">1</td>
      <td style="text-align:left">10</td>
      <td style="text-align:left"><b>logarithmic</b>
      </td>
      <td style="text-align:left">binary tree search</td>
    </tr>
    <tr>
      <td style="text-align:left">O(n)</td>
      <td style="text-align:left">10</td>
      <td style="text-align:left">100</td>
      <td style="text-align:left"><b>linear</b>
      </td>
      <td style="text-align:left">for loop</td>
    </tr>
    <tr>
      <td style="text-align:left">O(n log n)</td>
      <td style="text-align:left">10</td>
      <td style="text-align:left">1,000</td>
      <td style="text-align:left">?</td>
      <td style="text-align:left">linear loop after a binary tree search (all inside another loop)</td>
    </tr>
    <tr>
      <td style="text-align:left">O(n^2)</td>
      <td style="text-align:left">100</td>
      <td style="text-align:left">10,000</td>
      <td style="text-align:left"><b>quadratic</b>
      </td>
      <td style="text-align:left">nested for loop</td>
    </tr>
    <tr>
      <td style="text-align:left">O(2^n)</td>
      <td style="text-align:left">1,024</td>
      <td style="text-align:left">1.26 x 10^30</td>
      <td style="text-align:left"><b>exponential</b>
      </td>
      <td style="text-align:left">Fibonacci</td>
    </tr>
    <tr>
      <td style="text-align:left">O(n!)</td>
      <td style="text-align:left">3,628,800</td>
      <td style="text-align:left">(too long!)</td>
      <td style="text-align:left"><b>factorial</b>
      </td>
      <td style="text-align:left">
        <p>find all permutations (!)</p>
        <p>i.e. how many ways can you rearrange the letters of an n-letter word?
          n!</p>
      </td>
    </tr>
  </tbody>
</table>

As we go down the list, notice how much more time it takes, as `n` gets large...

...thus, we aim to program using _efficient_ data structures when we have large amounts of input!

