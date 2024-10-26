# Regularization
Create a Regularization optimized model for possum_dataset.csv dataset.  
The dataset has 104 observations and 7 variables: 
Independent Variables: 
Pop - population, either 0 (Victoria) or 1 (New South Wales or Queensland) 
Sex-  Either 0 (male) or 1 (female). 
Age- Age. 
head_l - Head length, in mm. 
skull_w - Skull width, in mm. 
tail_l-Tail length, in cm. 
Dependent Variable: 
total_l - Total length, in cm. 

![Screenshot 2024-10-26 141417](https://github.com/user-attachments/assets/f75a9695-d0df-4d65-b684-0a4ee3a05b57)
[ppt.pdf](https://github.com/user-attachments/files/17531603/ppt.pdf)
[Uploading COD<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"><html><head></head><body>















    




    
    
    
    

<div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[1]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">possum_dataset</span><span class="o">.</span><span class="n">csv</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output">
<pre>
<span class="ansi-red-intense-fg ansi-bold">---------------------------------------------------------------------------</span>
<span class="ansi-red-intense-fg ansi-bold">NameError</span>                                 Traceback (most recent call last)
Cell <span class="ansi-green-intense-fg ansi-bold">In[1], line 1</span>
<span class="ansi-green-intense-fg ansi-bold">----&gt; 1</span> <span class="ansi-yellow-bg">possum_dataset</span><span style="color: rgb(98,98,98);">.</span>csv

<span class="ansi-red-intense-fg ansi-bold">NameError</span>: name &#39;possum_dataset&#39; is not defined</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[2]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Load Libraries</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="o">%</span><span class="k">matplotlib</span> inline
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[3]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Load Dataset</span>
<span class="n">df1</span><span class="o">=</span><span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;./possum_dataset.csv&#39;</span><span class="p">)</span>
<span class="n">df1</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[3]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult">
<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>pop</th>
      <th>sex</th>
      <th>age</th>
      <th>head_l</th>
      <th>skull_w</th>
      <th>tail_l</th>
      <th>total_l</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>0</td>
      <td>8</td>
      <td>94.1</td>
      <td>60.4</td>
      <td>36.0</td>
      <td>89.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>1</td>
      <td>6</td>
      <td>92.5</td>
      <td>57.6</td>
      <td>36.5</td>
      <td>91.5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>1</td>
      <td>6</td>
      <td>94.0</td>
      <td>60.0</td>
      <td>39.0</td>
      <td>95.5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>1</td>
      <td>6</td>
      <td>93.2</td>
      <td>57.1</td>
      <td>38.0</td>
      <td>92.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>91.5</td>
      <td>56.3</td>
      <td>36.0</td>
      <td>85.5</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[4]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="n">df1</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[4]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult">
<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>pop</th>
      <th>sex</th>
      <th>age</th>
      <th>head_l</th>
      <th>skull_w</th>
      <th>tail_l</th>
      <th>total_l</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>104.000000</td>
      <td>104.000000</td>
      <td>104.000000</td>
      <td>104.000000</td>
      <td>104.000000</td>
      <td>104.000000</td>
      <td>104.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>0.557692</td>
      <td>0.413462</td>
      <td>3.817308</td>
      <td>92.602885</td>
      <td>56.883654</td>
      <td>37.009615</td>
      <td>87.088462</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.499066</td>
      <td>0.494839</td>
      <td>1.894112</td>
      <td>3.573349</td>
      <td>3.113426</td>
      <td>1.959518</td>
      <td>4.310549</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>82.500000</td>
      <td>50.000000</td>
      <td>32.000000</td>
      <td>75.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>2.750000</td>
      <td>90.675000</td>
      <td>54.975000</td>
      <td>35.875000</td>
      <td>84.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>3.000000</td>
      <td>92.800000</td>
      <td>56.350000</td>
      <td>37.000000</td>
      <td>88.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>5.000000</td>
      <td>94.725000</td>
      <td>58.100000</td>
      <td>38.000000</td>
      <td>90.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>9.000000</td>
      <td>103.100000</td>
      <td>68.600000</td>
      <td>43.000000</td>
      <td>96.500000</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[5]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Tukey Method</span>

<span class="c1"># Import required libraries</span>
<span class="kn">from</span> <span class="nn">collections</span> <span class="kn">import</span> <span class="n">Counter</span>

<span class="c1"># Outlier detection </span>
<span class="k">def</span> <span class="nf">detect_outliers</span><span class="p">(</span><span class="n">df</span><span class="p">,</span><span class="n">n</span><span class="p">,</span><span class="n">features</span><span class="p">):</span>
    
    <span class="n">outlier_indices</span> <span class="o">=</span> <span class="p">[]</span>
    
    <span class="c1"># iterate over features(columns)</span>
    <span class="k">for</span> <span class="n">col</span> <span class="ow">in</span> <span class="n">features</span><span class="p">:</span>
        <span class="c1"># 1st quartile (25%)</span>
        <span class="n">Q1</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">percentile</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="n">col</span><span class="p">],</span> <span class="mi">25</span><span class="p">)</span>
        <span class="c1"># 3rd quartile (75%)</span>
        <span class="n">Q3</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">percentile</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="n">col</span><span class="p">],</span><span class="mi">75</span><span class="p">)</span>
        <span class="c1"># Interquartile range (IQR)</span>
        <span class="n">IQR</span> <span class="o">=</span> <span class="n">Q3</span> <span class="o">-</span> <span class="n">Q1</span>
        
        <span class="c1"># outlier step</span>
        <span class="n">outlier_step</span> <span class="o">=</span> <span class="mf">1.5</span> <span class="o">*</span> <span class="n">IQR</span>
        
        <span class="c1"># Determine a list of indices of outliers for feature col</span>
        <span class="n">outlier_list_col</span> <span class="o">=</span> <span class="n">df</span><span class="p">[(</span><span class="n">df</span><span class="p">[</span><span class="n">col</span><span class="p">]</span> <span class="o">&lt;</span> <span class="n">Q1</span> <span class="o">-</span> <span class="n">outlier_step</span><span class="p">)</span> <span class="o">|</span> <span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="n">col</span><span class="p">]</span> <span class="o">&gt;</span> <span class="n">Q3</span> <span class="o">+</span> <span class="n">outlier_step</span> <span class="p">)]</span><span class="o">.</span><span class="n">index</span>
        
        <span class="c1"># append the found outlier indices for col to the list of outlier indices </span>
        <span class="n">outlier_indices</span><span class="o">.</span><span class="n">extend</span><span class="p">(</span><span class="n">outlier_list_col</span><span class="p">)</span>
        
    <span class="c1"># select observations containing more than 2 outliers</span>
    <span class="n">outlier_indices</span> <span class="o">=</span> <span class="n">Counter</span><span class="p">(</span><span class="n">outlier_indices</span><span class="p">)</span>        
    <span class="n">multiple_outliers</span> <span class="o">=</span> <span class="nb">list</span><span class="p">(</span> <span class="n">k</span> <span class="k">for</span> <span class="n">k</span><span class="p">,</span> <span class="n">v</span> <span class="ow">in</span> <span class="n">outlier_indices</span><span class="o">.</span><span class="n">items</span><span class="p">()</span> <span class="k">if</span> <span class="n">v</span> <span class="o">&gt;</span> <span class="n">n</span> <span class="p">)</span>
    
    <span class="k">return</span> <span class="n">multiple_outliers</span>

<span class="c1"># List of Outliers</span>
<span class="n">Outliers_to_drop</span> <span class="o">=</span> <span class="n">detect_outliers</span><span class="p">(</span><span class="n">df1</span><span class="p">,</span> <span class="mi">0</span><span class="p">,</span> <span class="nb">list</span><span class="p">(</span><span class="n">df1</span><span class="p">))</span>
<span class="n">df1</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">Outliers_to_drop</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[5]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult">
<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>pop</th>
      <th>sex</th>
      <th>age</th>
      <th>head_l</th>
      <th>skull_w</th>
      <th>tail_l</th>
      <th>total_l</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
      <td>93.4</td>
      <td>56.3</td>
      <td>37.0</td>
      <td>91.5</td>
    </tr>
    <tr>
      <th>10</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
      <td>93.3</td>
      <td>57.2</td>
      <td>39.0</td>
      <td>89.5</td>
    </tr>
    <tr>
      <th>54</th>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>103.1</td>
      <td>63.2</td>
      <td>38.0</td>
      <td>92.5</td>
    </tr>
    <tr>
      <th>58</th>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>102.5</td>
      <td>62.8</td>
      <td>40.0</td>
      <td>96.0</td>
    </tr>
    <tr>
      <th>72</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>82.5</td>
      <td>52.3</td>
      <td>36.5</td>
      <td>82.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>94.7</td>
      <td>67.7</td>
      <td>36.5</td>
      <td>89.5</td>
    </tr>
    <tr>
      <th>47</th>
      <td>1</td>
      <td>0</td>
      <td>5</td>
      <td>98.6</td>
      <td>63.2</td>
      <td>34.0</td>
      <td>85.0</td>
    </tr>
    <tr>
      <th>53</th>
      <td>1</td>
      <td>0</td>
      <td>7</td>
      <td>96.9</td>
      <td>63.0</td>
      <td>43.0</td>
      <td>91.5</td>
    </tr>
    <tr>
      <th>57</th>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>94.5</td>
      <td>64.2</td>
      <td>39.0</td>
      <td>91.0</td>
    </tr>
    <tr>
      <th>78</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>85.8</td>
      <td>50.0</td>
      <td>36.5</td>
      <td>81.0</td>
    </tr>
    <tr>
      <th>97</th>
      <td>1</td>
      <td>0</td>
      <td>5</td>
      <td>93.2</td>
      <td>68.6</td>
      <td>35.0</td>
      <td>84.0</td>
    </tr>
    <tr>
      <th>41</th>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>85.3</td>
      <td>54.1</td>
      <td>32.0</td>
      <td>77.0</td>
    </tr>
    <tr>
      <th>42</th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>90.0</td>
      <td>55.5</td>
      <td>32.0</td>
      <td>81.0</td>
    </tr>
    <tr>
      <th>86</th>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>98.5</td>
      <td>60.7</td>
      <td>41.5</td>
      <td>93.0</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[6]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Create New Dataset without Outliers</span>
<span class="n">good_data</span> <span class="o">=</span> <span class="n">df1</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">df1</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="n">Outliers_to_drop</span><span class="p">])</span><span class="o">.</span><span class="n">reset_index</span><span class="p">(</span><span class="n">drop</span> <span class="o">=</span> <span class="kc">True</span><span class="p">)</span>
<span class="n">good_data</span><span class="o">.</span><span class="n">info</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output">
<pre>&lt;class &#39;pandas.core.frame.DataFrame&#39;&gt;
RangeIndex: 90 entries, 0 to 89
Data columns (total 7 columns):
 #   Column   Non-Null Count  Dtype  
---  ------   --------------  -----  
 0   pop      90 non-null     int64  
 1   sex      90 non-null     int64  
 2   age      90 non-null     int64  
 3   head_l   90 non-null     float64
 4   skull_w  90 non-null     float64
 5   tail_l   90 non-null     float64
 6   total_l  90 non-null     float64
dtypes: float64(4), int64(3)
memory usage: 5.0 KB
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[7]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Create Standard Model</span>

<span class="c1">#Define x and y variable</span>
<span class="n">x</span> <span class="o">=</span> <span class="n">good_data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="s1">&#39;total_l&#39;</span><span class="p">,</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span><span class="o">.</span><span class="n">to_numpy</span><span class="p">()</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">good_data</span><span class="p">[</span><span class="s1">&#39;total_l&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">to_numpy</span><span class="p">()</span>

<span class="c1">#Create Train and Test Datasets</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">train_test_split</span>
<span class="n">x_train</span><span class="p">,</span><span class="n">x_test</span><span class="p">,</span><span class="n">y_train</span><span class="p">,</span><span class="n">y_test</span><span class="o">=</span><span class="n">train_test_split</span><span class="p">(</span><span class="n">x</span><span class="p">,</span><span class="n">y</span><span class="p">,</span><span class="n">test_size</span><span class="o">=</span><span class="mf">0.2</span><span class="p">,</span><span class="n">random_state</span><span class="o">=</span><span class="mi">100</span><span class="p">)</span>

<span class="c1">#Scale the Data</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">StandardScaler</span>
<span class="n">sc</span> <span class="o">=</span> <span class="n">StandardScaler</span><span class="p">()</span>
<span class="n">x_train2</span> <span class="o">=</span> <span class="n">sc</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">x_train</span><span class="p">)</span>
<span class="n">x_test2</span> <span class="o">=</span> <span class="n">sc</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="n">x_test</span><span class="p">)</span>

<span class="c1">#Models</span>
<span class="kn">from</span> <span class="nn">sklearn.linear_model</span> <span class="kn">import</span> <span class="n">LinearRegression</span><span class="p">,</span> <span class="n">Lasso</span><span class="p">,</span> <span class="n">Ridge</span><span class="p">,</span> <span class="n">ElasticNet</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[8]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1"># Construct some pipelines </span>
<span class="kn">from</span> <span class="nn">sklearn.pipeline</span> <span class="kn">import</span> <span class="n">Pipeline</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">StandardScaler</span>

<span class="c1">#Create Pipeline</span>

<span class="n">pipeline</span> <span class="o">=</span><span class="p">[]</span>

<span class="n">pipe_lm</span> <span class="o">=</span> <span class="n">Pipeline</span><span class="p">([(</span><span class="s1">&#39;scl&#39;</span><span class="p">,</span> <span class="n">StandardScaler</span><span class="p">()),</span>
                    <span class="p">(</span><span class="s1">&#39;clf&#39;</span><span class="p">,</span> <span class="n">LinearRegression</span><span class="p">())])</span>
<span class="n">pipeline</span><span class="o">.</span><span class="n">insert</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="n">pipe_lm</span><span class="p">)</span>

<span class="n">pipe_lasso</span><span class="o">=</span> <span class="n">Pipeline</span><span class="p">([(</span><span class="s1">&#39;scl&#39;</span><span class="p">,</span> <span class="n">StandardScaler</span><span class="p">()),</span>
                     <span class="p">(</span><span class="s1">&#39;clf&#39;</span><span class="p">,</span> <span class="n">Lasso</span><span class="p">(</span><span class="n">random_state</span><span class="o">=</span><span class="mi">100</span><span class="p">))])</span>
<span class="n">pipeline</span><span class="o">.</span><span class="n">insert</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="n">pipe_lasso</span><span class="p">)</span>

<span class="n">pipe_ridge</span><span class="o">=</span> <span class="n">Pipeline</span><span class="p">([(</span><span class="s1">&#39;scl&#39;</span><span class="p">,</span> <span class="n">StandardScaler</span><span class="p">()),</span>
                     <span class="p">(</span><span class="s1">&#39;clf&#39;</span><span class="p">,</span> <span class="n">Ridge</span><span class="p">(</span><span class="n">random_state</span><span class="o">=</span><span class="mi">100</span><span class="p">))])</span>
<span class="n">pipeline</span><span class="o">.</span><span class="n">insert</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="n">pipe_ridge</span><span class="p">)</span>

<span class="n">pipe_elas</span><span class="o">=</span> <span class="n">Pipeline</span><span class="p">([(</span><span class="s1">&#39;scl&#39;</span><span class="p">,</span> <span class="n">StandardScaler</span><span class="p">()),</span>
                     <span class="p">(</span><span class="s1">&#39;clf&#39;</span><span class="p">,</span> <span class="n">ElasticNet</span><span class="p">(</span><span class="n">random_state</span><span class="o">=</span><span class="mi">100</span><span class="p">))])</span>
<span class="n">pipeline</span><span class="o">.</span><span class="n">insert</span><span class="p">(</span><span class="mi">3</span><span class="p">,</span><span class="n">pipe_elas</span><span class="p">)</span>

<span class="c1"># Set grid search params </span>

<span class="n">modelpara</span> <span class="o">=</span><span class="p">[]</span>

<span class="n">param_gridlm</span> <span class="o">=</span> <span class="p">{}</span>
<span class="n">modelpara</span><span class="o">.</span><span class="n">insert</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="n">param_gridlm</span><span class="p">)</span>

<span class="n">param_gridlasso</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;clf__alpha&#39;</span><span class="p">:[</span><span class="mf">1e-15</span><span class="p">,</span> <span class="mf">1e-10</span><span class="p">,</span> <span class="mf">1e-8</span><span class="p">,</span> <span class="mf">1e-4</span><span class="p">,</span> <span class="mf">1e-3</span><span class="p">,</span><span class="mf">1e-2</span><span class="p">,</span> <span class="mf">1e-1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">10</span><span class="p">,</span> <span class="mi">20</span><span class="p">],</span>
                  <span class="s1">&#39;clf__tol&#39;</span><span class="p">:[</span><span class="mf">1e-1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">10</span><span class="p">,</span> <span class="mi">20</span><span class="p">,</span> <span class="mi">50</span><span class="p">,</span> <span class="mi">100</span><span class="p">]}</span>
<span class="n">modelpara</span><span class="o">.</span><span class="n">insert</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="n">param_gridlasso</span><span class="p">)</span>

<span class="n">param_gridridge</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;clf__alpha&#39;</span><span class="p">:[</span><span class="mf">1e-15</span><span class="p">,</span> <span class="mf">1e-10</span><span class="p">,</span> <span class="mf">1e-8</span><span class="p">,</span> <span class="mf">1e-4</span><span class="p">,</span> <span class="mf">1e-3</span><span class="p">,</span><span class="mf">1e-2</span><span class="p">,</span> <span class="mf">1e-1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">10</span><span class="p">,</span> <span class="mi">20</span><span class="p">],</span>
                  <span class="s1">&#39;clf__tol&#39;</span><span class="p">:[</span><span class="mf">1e-1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">10</span><span class="p">,</span> <span class="mi">20</span><span class="p">,</span> <span class="mi">50</span><span class="p">,</span> <span class="mi">100</span><span class="p">]}</span>
<span class="n">modelpara</span><span class="o">.</span><span class="n">insert</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="n">param_gridridge</span><span class="p">)</span>

<span class="n">param_gridelas</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;clf__alpha&#39;</span><span class="p">:[</span><span class="mf">1e-15</span><span class="p">,</span> <span class="mf">1e-10</span><span class="p">,</span> <span class="mf">1e-8</span><span class="p">,</span> <span class="mf">1e-4</span><span class="p">,</span> <span class="mf">1e-3</span><span class="p">,</span><span class="mf">1e-2</span><span class="p">,</span> <span class="mf">1e-1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">10</span><span class="p">,</span> <span class="mi">20</span><span class="p">],</span>
                 <span class="s1">&#39;clf__tol&#39;</span><span class="p">:[</span><span class="mf">1e-1</span><span class="p">,</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">10</span><span class="p">,</span> <span class="mi">20</span><span class="p">,</span> <span class="mi">50</span><span class="p">,</span> <span class="mi">100</span><span class="p">]}</span>
<span class="n">modelpara</span><span class="o">.</span><span class="n">insert</span><span class="p">(</span><span class="mi">3</span><span class="p">,</span><span class="n">param_gridelas</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[9]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Create Learning Curves</span>

<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">learning_curve</span>

<span class="k">def</span> <span class="nf">plot_learning_curves</span><span class="p">(</span><span class="n">model</span><span class="p">):</span>
    <span class="n">train_sizes</span><span class="p">,</span> <span class="n">train_scores</span><span class="p">,</span> <span class="n">test_scores</span> <span class="o">=</span> <span class="n">learning_curve</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">model</span><span class="p">,</span>
                                                            <span class="n">X</span><span class="o">=</span><span class="n">x_train</span><span class="p">,</span> 
                                                            <span class="n">y</span><span class="o">=</span><span class="n">y_train</span><span class="p">,</span>
                                                            <span class="n">train_sizes</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">linspace</span><span class="p">(</span><span class="mf">.1</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">10</span><span class="p">),</span>
                                                            <span class="n">scoring</span> <span class="o">=</span> <span class="s1">&#39;neg_root_mean_squared_error&#39;</span><span class="p">,</span>
                                                            <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span><span class="n">random_state</span><span class="o">=</span><span class="mi">100</span><span class="p">)</span>
    
    <span class="n">train_mean</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="o">-</span><span class="n">train_scores</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
    <span class="n">train_std</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">std</span><span class="p">(</span><span class="o">-</span><span class="n">train_scores</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
    <span class="n">test_mean</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="o">-</span><span class="n">test_scores</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
    <span class="n">test_std</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">std</span><span class="p">(</span><span class="o">-</span><span class="n">test_scores</span><span class="p">,</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
    
    <span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">train_sizes</span><span class="p">,</span> <span class="n">train_mean</span><span class="p">,</span><span class="n">color</span><span class="o">=</span><span class="s1">&#39;blue&#39;</span><span class="p">,</span> <span class="n">marker</span><span class="o">=</span><span class="s1">&#39;o&#39;</span><span class="p">,</span> 
             <span class="n">markersize</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">label</span><span class="o">=</span><span class="s1">&#39;training accuracy&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">fill_between</span><span class="p">(</span><span class="n">train_sizes</span><span class="p">,</span> <span class="n">train_mean</span> <span class="o">+</span> <span class="n">train_std</span><span class="p">,</span> <span class="n">train_mean</span> <span class="o">-</span> <span class="n">train_std</span><span class="p">,</span>
                     <span class="n">alpha</span><span class="o">=</span><span class="mf">0.15</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;blue&#39;</span><span class="p">)</span>

    <span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">train_sizes</span><span class="p">,</span> <span class="n">test_mean</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;green&#39;</span><span class="p">,</span> <span class="n">linestyle</span><span class="o">=</span><span class="s1">&#39;--&#39;</span><span class="p">,</span> <span class="n">marker</span><span class="o">=</span><span class="s1">&#39;s&#39;</span><span class="p">,</span> <span class="n">markersize</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span>
             <span class="n">label</span><span class="o">=</span><span class="s1">&#39;validation accuracy&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">fill_between</span><span class="p">(</span><span class="n">train_sizes</span><span class="p">,</span> <span class="n">test_mean</span> <span class="o">+</span> <span class="n">test_std</span><span class="p">,</span> <span class="n">test_mean</span> <span class="o">-</span> <span class="n">test_std</span><span class="p">,</span>
                     <span class="n">alpha</span><span class="o">=</span><span class="mf">0.15</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;green&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">grid</span><span class="p">()</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Number of training samples&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;RMSE&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">(</span><span class="n">loc</span><span class="o">=</span><span class="s1">&#39;best&#39;</span><span class="p">)</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">ylim</span><span class="p">([</span><span class="o">-</span><span class="mi">1</span><span class="p">,</span><span class="mi">10</span><span class="p">])</span>
    <span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[10]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Plot Learning Curve</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Learning Curve - LM&#39;</span><span class="p">)</span>
<span class="n">plot_learning_curves</span><span class="p">(</span><span class="n">pipe_lm</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Learning Curve - Lasso&#39;</span><span class="p">)</span>
<span class="n">plot_learning_curves</span><span class="p">(</span><span class="n">pipe_lasso</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Learning Curve - Ridge&#39;</span><span class="p">)</span>
<span class="n">plot_learning_curves</span><span class="p">(</span><span class="n">pipe_ridge</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Learning Curve - ElasticNet&#39;</span><span class="p">)</span>
<span class="n">plot_learning_curves</span><span class="p">(</span><span class="n">pipe_elas</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output">
<pre>Learning Curve - LM
</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output">
<img src="javascript://"/>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output">
<pre>Learning Curve - Lasso
</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output">
<img src="javascript://"/>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output">
<pre>Learning Curve - Ridge
</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output">
<img src="javascript://"/>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output">
<pre>Learning Curve - ElasticNet
</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output">
<img src="javascript://"/>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[11]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Model Analysis</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">RepeatedKFold</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">cross_val_score</span>

<span class="n">models</span><span class="o">=</span><span class="p">[]</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">((</span><span class="s1">&#39;LinearRegression&#39;</span><span class="p">,</span><span class="n">pipe_lm</span><span class="p">))</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">((</span><span class="s1">&#39;Lasso&#39;</span><span class="p">,</span><span class="n">pipe_lasso</span><span class="p">))</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">((</span><span class="s1">&#39;Ridge&#39;</span><span class="p">,</span><span class="n">pipe_ridge</span><span class="p">))</span>
<span class="n">models</span><span class="o">.</span><span class="n">append</span><span class="p">((</span><span class="s1">&#39;ElasticNet&#39;</span><span class="p">,</span><span class="n">pipe_elas</span><span class="p">))</span>
  
<span class="c1">#Model Evaluation</span>
<span class="n">results</span> <span class="o">=</span><span class="p">[]</span>
<span class="n">names</span><span class="o">=</span><span class="p">[]</span>
<span class="n">scoring</span> <span class="o">=</span><span class="s1">&#39;neg_root_mean_squared_error&#39;</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Model Evaluation - RMSE&#39;</span><span class="p">)</span>
<span class="k">for</span> <span class="n">name</span><span class="p">,</span> <span class="n">model</span> <span class="ow">in</span> <span class="n">models</span><span class="p">:</span>
    <span class="n">rkf</span><span class="o">=</span><span class="n">RepeatedKFold</span><span class="p">(</span><span class="n">n_splits</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">n_repeats</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">100</span><span class="p">)</span>
    <span class="n">cv_results</span> <span class="o">=</span> <span class="n">cross_val_score</span><span class="p">(</span><span class="n">model</span><span class="p">,</span><span class="n">x_train</span><span class="p">,</span><span class="n">y_train</span><span class="p">,</span><span class="n">cv</span><span class="o">=</span><span class="n">rkf</span><span class="p">,</span><span class="n">scoring</span><span class="o">=</span><span class="n">scoring</span><span class="p">)</span>
    <span class="n">results</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="o">-</span><span class="n">cv_results</span><span class="p">))</span>
    <span class="n">names</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">name</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="si">{}</span><span class="s1"> </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">name</span><span class="p">,</span><span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="o">-</span><span class="n">cv_results</span><span class="o">.</span><span class="n">mean</span><span class="p">())))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">&#39;</span><span class="p">)</span>

<span class="c1">#Boxplot View</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">5</span><span class="p">))</span>
<span class="n">fig</span><span class="o">.</span><span class="n">suptitle</span><span class="p">(</span><span class="s1">&#39;Boxplot View&#39;</span><span class="p">)</span>
<span class="n">ax</span> <span class="o">=</span> <span class="n">fig</span><span class="o">.</span><span class="n">add_subplot</span><span class="p">(</span><span class="mi">111</span><span class="p">)</span>
<span class="n">sns</span><span class="o">.</span><span class="n">boxplot</span><span class="p">(</span><span class="n">data</span><span class="o">=</span><span class="n">results</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">set_xticklabels</span><span class="p">(</span><span class="n">names</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;RMSE&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Model&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output">
<pre>Model Evaluation - RMSE
LinearRegression 1.53
Lasso 1.73
Ridge 1.53
ElasticNet 1.67


</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output">
<img src="javascript://"/>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[12]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Define Gridsearch Function</span>

<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">GridSearchCV</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="kn">import</span> <span class="n">metrics</span>

<span class="k">def</span> <span class="nf">Gridsearch_cv</span><span class="p">(</span><span class="n">model</span><span class="p">,</span> <span class="n">params</span><span class="p">):</span>
    
    <span class="c1">#Cross-validation Function</span>
    <span class="n">cv2</span><span class="o">=</span><span class="n">RepeatedKFold</span><span class="p">(</span><span class="n">n_splits</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">n_repeats</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">100</span><span class="p">)</span>
        
    <span class="c1">#GridSearch CV</span>
    <span class="n">gs_clf</span> <span class="o">=</span> <span class="n">GridSearchCV</span><span class="p">(</span><span class="n">model</span><span class="p">,</span> <span class="n">params</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="n">cv2</span><span class="p">,</span><span class="n">scoring</span><span class="o">=</span><span class="s1">&#39;neg_root_mean_squared_error&#39;</span><span class="p">)</span>
    <span class="n">gs_clf</span> <span class="o">=</span> <span class="n">gs_clf</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">x_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
    <span class="n">model</span> <span class="o">=</span> <span class="n">gs_clf</span><span class="o">.</span><span class="n">best_estimator_</span>
    
    <span class="c1"># Use best model and test data for final evaluation</span>
    <span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">x_test</span><span class="p">)</span>

    <span class="c1">#Identify Best Parameters to Optimize the Model</span>
    <span class="n">bestpara</span><span class="o">=</span><span class="nb">str</span><span class="p">(</span><span class="n">gs_clf</span><span class="o">.</span><span class="n">best_params_</span><span class="p">)</span>
   
    <span class="c1">#Output Heading</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">Optimized Model&#39;</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">Model Name:&#39;</span><span class="p">,</span><span class="nb">str</span><span class="p">(</span><span class="n">pipeline</span><span class="o">.</span><span class="n">named_steps</span><span class="p">[</span><span class="s1">&#39;clf&#39;</span><span class="p">]))</span>
        
    <span class="c1">#Output Validation Statistics</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">Best Parameters:&#39;</span><span class="p">,</span><span class="n">bestpara</span><span class="p">)</span>
    
    <span class="c1">#Test data accuracy of model with best params    </span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">Intercept: </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="nb">float</span><span class="p">(</span><span class="n">gs_clf</span><span class="o">.</span><span class="n">best_estimator_</span><span class="o">.</span><span class="n">named_steps</span><span class="p">[</span><span class="s1">&#39;clf&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">intercept_</span><span class="p">)))</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">Model coefficients: &#39;</span><span class="p">)</span>   
    <span class="k">for</span> <span class="n">name</span><span class="p">,</span> <span class="n">score</span> <span class="ow">in</span> <span class="nb">zip</span><span class="p">(</span><span class="nb">list</span><span class="p">(</span><span class="n">good_data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="s1">&#39;total_l&#39;</span><span class="p">,</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)),</span>
                           <span class="n">gs_clf</span><span class="o">.</span><span class="n">best_estimator_</span><span class="o">.</span><span class="n">named_steps</span><span class="p">[</span><span class="s1">&#39;clf&#39;</span><span class="p">]</span><span class="o">.</span><span class="n">coef_</span><span class="p">):</span>
         <span class="nb">print</span><span class="p">(</span><span class="n">name</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">score</span><span class="p">,</span><span class="mi">2</span><span class="p">))</span> 
    
    <span class="c1">#Print R2</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">R2: </span><span class="si">{:0.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">metrics</span><span class="o">.</span><span class="n">r2_score</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span><span class="n">y_pred</span><span class="p">)))</span>
    <span class="n">adjusted_r_squared2</span> <span class="o">=</span> <span class="mi">1</span><span class="o">-</span><span class="p">(</span><span class="mi">1</span><span class="o">-</span><span class="n">metrics</span><span class="o">.</span><span class="n">r2_score</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span><span class="n">y_pred</span><span class="p">))</span><span class="o">*</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">y</span><span class="p">)</span><span class="o">-</span><span class="mi">1</span><span class="p">)</span><span class="o">/</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">y</span><span class="p">)</span><span class="o">-</span><span class="n">x</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">-</span><span class="mi">1</span><span class="p">)</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Adj_R2: </span><span class="si">{:0.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">adjusted_r_squared2</span><span class="p">))</span>        
      
    <span class="c1">#Print MSE and RMSE</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">Mean Absolute Error: </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">metrics</span><span class="o">.</span><span class="n">mean_absolute_error</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">)))</span>  
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Mean Squared Error: </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">metrics</span><span class="o">.</span><span class="n">mean_squared_error</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">)))</span>  
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Root Mean Squared Error: </span><span class="si">{:.2f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="n">metrics</span><span class="o">.</span><span class="n">mean_squared_error</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))))</span> 
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[13]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span><span class="c1">#Run Models</span>
<span class="k">for</span> <span class="n">pipeline</span><span class="p">,</span> <span class="n">modelpara</span> <span class="ow">in</span> <span class="nb">zip</span><span class="p">(</span><span class="n">pipeline</span><span class="p">,</span><span class="n">modelpara</span><span class="p">):</span>
    <span class="n">Gridsearch_cv</span><span class="p">(</span><span class="n">pipeline</span><span class="p">,</span><span class="n">modelpara</span><span class="p">)</span> 
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output">
<pre>
Optimized Model

Model Name: LinearRegression()

Best Parameters: {}

Intercept: 87.25

Model coefficients: 
pop -1.38
sex 0.75
age -0.15
head_l 1.72
skull_w 0.63
tail_l 2.04

R2: 0.76
Adj_R2: 0.75

Mean Absolute Error: 1.75
Mean Squared Error: 4.40
Root Mean Squared Error: 2.10

Optimized Model

Model Name: Lasso(random_state=100)

Best Parameters: {&#39;clf__alpha&#39;: 0.1, &#39;clf__tol&#39;: 0.1}

Intercept: 87.25

Model coefficients: 
pop -1.04
sex 0.72
age -0.0
head_l 1.66
skull_w 0.64
tail_l 1.74

R2: 0.73
Adj_R2: 0.71

Mean Absolute Error: 1.87
Mean Squared Error: 4.98
Root Mean Squared Error: 2.23

Optimized Model

Model Name: Ridge(random_state=100)

Best Parameters: {&#39;clf__alpha&#39;: 5, &#39;clf__tol&#39;: 0.1}

Intercept: 87.25

Model coefficients: 
pop -1.15
sex 0.74
age -0.1
head_l 1.58
skull_w 0.74
tail_l 1.77

R2: 0.74
Adj_R2: 0.72

Mean Absolute Error: 1.85
Mean Squared Error: 4.89
Root Mean Squared Error: 2.21

Optimized Model

Model Name: ElasticNet(random_state=100)

Best Parameters: {&#39;clf__alpha&#39;: 0.01, &#39;clf__tol&#39;: 0.1}

Intercept: 87.25

Model coefficients: 
pop -1.32
sex 0.75
age -0.15
head_l 1.69
skull_w 0.67
tail_l 1.98

R2: 0.76
Adj_R2: 0.74

Mean Absolute Error: 1.77
Mean Squared Error: 4.50
Root Mean Squared Error: 2.12
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&#160;[&#160;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor">
     <div class="CodeMirror cm-s-jupyter">
<div class="highlight hl-ipython3"><pre><span></span> 
</pre></div>

     </div>
</div>
</div>
</div>

</div>









<script type="module" src="https://s.brightspace.com/lib/bsi/2024.10.209/unbundled/mathjax.js"></script><script type="text/javascript">document.addEventListener('DOMContentLoaded', function() {
						if (document.querySelector('math') || /\$\$|\\\(|\\\[|\\begin{|\\ref{|\\eqref{/.test(document.body.innerHTML)) {
							document.querySelectorAll('mspace[linebreak="newline"]').forEach(elm => {
								elm.setAttribute('style', 'display: block; height: 0.5rem;');
							});

							window.D2L.MathJax.loadMathJax({
								outputScale: 1.5,
								renderLatex: false,
								enableMML3Support: false
							});
						}
					});</script><script type="module" src="https://s.brightspace.com/lib/bsi/2024.10.209/unbundled/prism.js"></script><script type="text/javascript">document.addEventListener('DOMContentLoaded', function() {
					document.querySelectorAll('.d2l-code').forEach(code => {
						window.D2L.Prism.formatCodeElement(code);
					});
				});</script><script type="module" src="https://s.brightspace.com/lib/bsi/2024.10.209/unbundled/embeds.js"></script><script type="text/javascript">document.addEventListener('DOMContentLoaded', function() {
					window.D2L.EmbedRenderer.renderEmbeds(document.body);
				});</script></body></html>E.html…]()
