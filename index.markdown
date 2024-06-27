---
layout: mydefault
---

<html>

<head>
  <meta charset="utf-8">
  <meta name="robots" content="index,follow">
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=yes">
  <meta name="description" content="CodeLMSec Benchmark: Systematically Evaluating and Finding Security Vulnerabilities in Black-Box Code Language Models">
  <meta name="keywords" content="CodeLMSec, code-generation, large-language-model, benchmark">
  <meta name="google-site-verification" content="arngK7N6odVkEFrVU3iLqYio_pLlBzKovcuq1MXoMQA" />
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>CodeLMSec Benchmark: Systematically Evaluating and Finding Security Vulnerabilities in Black-Box Code Language Models</title>

  <link href="https://fonts.googleapis.com/css?family=Google+Sans|Noto+Sans|Castoro" rel="stylesheet">

  <link rel="stylesheet" href="./static/css/bulma.min.css">
  <link rel="stylesheet" href="./static/css/bulma-carousel.min.css">
  <link rel="stylesheet" href="./static/css/bulma-slider.min.css">
  <link rel="stylesheet" href="./static/css/fontawesome.all.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/jpswalsh/academicons@1/css/academicons.min.css">
  <link rel="stylesheet" href="./static/css/index.css">

  <link rel="stylesheet" href="./bower_components/bootstrap/dist/css/bootstrap.table.min.css">
  <!--  <link rel="stylesheet" href="bower_components/bootstrap/dist/css/bootstrap.min.css">-->
  <link rel="stylesheet" href="./stylesheets/layout.css">
  <link rel="stylesheet" href="./stylesheets/index.css">

  <!-- for print the table -->
  <script type="text/javascript" charset="utf8" src="https://code.jquery.com/jquery-3.6.0.slim.min.js"></script>

  <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.11.3/css/jquery.dataTables.css">
  <script type="text/javascript" charset="utf8" src="https://cdn.datatables.net/1.11.3/js/jquery.dataTables.js"></script>

  <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.11.3/css/dataTables.bootstrap5.min.css">
  <script src="https://cdn.datatables.net/1.11.3/js/dataTables.bootstrap5.min.js"></script>

  <!-- <link rel="icon" href="./static/images/inficoder_eval_logo2.png"> -->

  <script defer src="./static/js/fontawesome.all.min.js"></script>
  <script src="./static/js/bulma-carousel.min.js"></script>
  <script src="./static/js/bulma-slider.min.js"></script>
  <script src="./static/js/index.js"></script>
</head>

<body>

  <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>
    <div class="navbar-menu">
      <div class="navbar-start" style="flex-grow: 1; justify-content: center;">
        <a class="navbar-item" href="https://github.com/codelmsec">
          <span class="icon">
            <i class="fas fa-home"></i>
          </span>
        </a>
        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            More
          </a>
          <div class="navbar-dropdown">
            <a class="navbar-item" href="https://github.com/codelmsec">
              CodeLMSec Organization
            </a>
          </div>
        </div>
      </div>

    </div>
  </nav>


  <section class="hero">
    <div class="hero-body">
      <div class="container is-max-desktop">
        <div class="columns is-centered">
          <div class="column has-text-centered">
            <h3 class="title is-1 publication-title">CodeLMSec Benchmark: Systematically Evaluating and Finding Security Vulnerabilities in Black-Box Code Language Models 
            </h3>
            <div class="is-size-5 publication-authors">
              <span class="author-block">
                <a href="https://hajipour.github.io/">Hossein Hajipour</a>,</span>
              <span class="author-block">
                <a href="https://keno-hassler.de/">Keno Hassler</a>,</span>
              <span class="author-block">
                <a href="https://cispa.de/en/research/groups/holz">Thorsten Holz</a>,
              </span>
              <span class="author-block">
                <a href="https://leaschoenherr.me/">Lea Schönherr</a>,
              </span>
              <span class="author-block">
                <a href="https://cispa.saarland/group/fritz/">Mario Fritz</a>
              </span>
            </div>
             <div class="is-size-5 publication-authors">
              <span class="author-block">CISPA Helmholtz Center for Information Security</span>
            </div>
            <div class="column has-text-centered">
              <div class="publication-links">
                <!-- PDF Link. -->
                <span class="link-block">
                  <a href="https://arxiv.org/abs/2302.04012"
                    class="external-link button is-normal is-rounded is-dark" target='_blank'>
                    <span class="icon">
                      <i class="fas fa-file-pdf"></i>
                    </span>
                    <span>Paper</span>
                  </a>
                </span>
                <!-- Dataset Link. -->
                <span class="link-block">
                  <a href="https://github.com/codelmsec/codelmsec"
                     class="external-link button is-normal is-rounded is-dark" target='_blank'>
                    <span class="icon">
                      <i class="fab fa-github"></i>
                    </span>
                    <span>Code and Data</span>
                  </a>
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>


  <section class="section">
    <div class="container is-max-desktop">
      <!-- Abstract. -->
      <div class="columns is-centered has-text-centered">
        <div class="column is-four-fifths">
          <h2 class="title is-3">Abstract</h2>
          <div class="content has-text-justified">
            <p>
              Large language models (LLMs) for automatic code generation have recently achieved breakthroughs in several programming tasks. Their advances in competition-level programming problems have made them an essential pillar of AI-assisted pair programming, and tools such as GitHub Copilot have emerged as part of the daily programming workflow used by millions of developers. Training data for these models is usually collected from the Internet (e.g., from open-source repositories) and is likely to contain faults and security vulnerabilities. This unsanitized training data can cause the language models to learn these vulnerabilities and propagate them during the code generation procedure. While these models have been extensively evaluated for their ability to produce functionally correct programs, there remains a lack of comprehensive investigations and benchmarks addressing the security aspects of these models.
              <br>In this work, we propose a method to systematically study the security issues of code language models to assess their susceptibility to generating vulnerable code. To this end, we introduce the first approach to automatically find generated code that contains vulnerabilities in black-box code generation models. This involves proposing a novel few-shot prompting approach. We evaluate the effectiveness of our approach by examining code language models in generating high-risk security weaknesses. Furthermore, we use our method to create a collection of diverse non-secure prompts for various vulnerability scenarios. This dataset serves as a benchmark to evaluate and compare the security weaknesses of code language models.

            </p>
          </div>
        </div>
      </div>
      <!--/ Abstract. -->
    </div>
  </section>



  <section class="section">
    <div class="cover" id="contentCover">
      <!-- Baseline. -->
      <div class="container-t">
        <div class="row">
          <div class="col-md-12">
            <div class="infoCard">
              <div class="infoBody">
                <p align="left">
                  <div class="left"><b>CodeLM Security Benchmark</b>: We employ our proposed non-secure prompts dataset as a benchmark to assess and evaluate different large language models (LLMs). This dataset contains 280 non-secure prompts, with 200 designed for Python and 80 for C. We evaluate the security vulnerabilities issues that can be generated by these models through the following steps:
                  <br>
                  <br>
                  <ol style="list-style-position: inside">
                    <li>Using a LLM (e.g., CodeGen-6B) to generate code completion for each non-secure prompt.</li>
                    <li>Consider each non-secure prompt and the corresponding generated code completion(s) as a complete code(s).</li>
                    <li>Employ CodeQL security analyzer to spot security issues in the generated codes.</li>
                  </ol>
                  <br>
                  </div>
                </p>
                <p align="left">
                  <div class="left">
                  To generate code completion for each non-secure prompts we use the following settings: a maximum token limit of 512, using nucleus sampling to sample 5 completion, a top-p value of 0.95, and a temperature of 0.2.
                  </div>
                </p>
                <p align="left">
                  <div class="left">
                  <br>
                  <b> Notice:</b> The following table shows the number of vulnerable Python and C codes generated by various models using our non-secure prompt dataset. The top-1 column displays the number of vulnerable codes in the top-ranked output of the model. The top-5 column shows the number of vulnerable codes among the five most probable model outputs.
                  </div>
                </p>
                <br>
                <table class="table maintable stripe hover row-border order-column" id="maintable">
                  <thead>
                    <tr>
                      <th>Model Name</th>
                      <th>top-1 (Python)</th>
                      <th>top-5 (Python)</th>
                      <th>top-1 (C)</th>
                      <th>top-5 (C)</th>
                    </tr>
                  </thead>
                  <tbody>
                    {% for item in site.data.benchmark.records %}
                    <tr>
                      <td>{{ item.title }}</td>                      
                      <td>{{ item.top_1_py }}</td>
                      <td>{{ item.top_5_py }}</td>
                      <td>{{ item.top_1_c }}</td>
                      <td>{{ item.top_5_c }}</td>
                    </tr>
                    {% endfor %}
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- Python detailed. -->
      <div class="container-t">
        <div class="row">
          <div class="col-md-12">
            <div class="infoCard">
              <div class="infoBody">
                <p align="left">
                  <div class="left"><b>Notice:</b> The following table shows the number of vulnerable Python codes generated by various models using our non-secure prompt dataset. The results demonstrate the number of generated vulnerable codes among the five most probable model outputs. Columns two to eleven provide details results generating codes for various CWEs. Column twelve provides the number of found vulnerable codes with the other CWEs that CodeQL queries. The last column provides the sum of all codes with at least one security vulnerability.
                  </div>
                </p>
                <br>
                <table class="table python stripe hover row-border order-column" id="python" style="width:80%">
                  <thead>
                    <tr>
                      <th>Model Name</th>
                      <th>CWE-020</th>
                      <th>CWE-022</th>
                      <th>CWE-078</th>
                      <th>CWE-079</th>
                      <th>CWE-089</th>
                      <th>CWE-094</th>
                      <th>CWE-117</th>
                      <th>CWE-502</th>
                      <th>CWE-601</th>
                      <th>CWE-611</th>
                      <th>Other</th>
                      <th>Total</th>
                    </tr>
                  </thead>
                  <tbody>
                    {% for item in site.data.details_python.records %}
                    <tr>
                      <td>{{ item.title }}</td>                      
                      <td>{{ item.cwe_020 }}</td>
                      <td>{{ item.cwe_022 }}</td>
                      <td>{{ item.cwe_078 }}</td>
                      <td>{{ item.cwe_079 }}</td>
                      <td>{{ item.cwe_089 }}</td>
                      <td>{{ item.cwe_094 }}</td>
                      <td>{{ item.cwe_117 }}</td>
                      <td>{{ item.cwe_502 }}</td>
                      <td>{{ item.cwe_601 }}</td>
                      <td>{{ item.cwe_611 }}</td>
                      <td>{{ item.other }}</td>
                      <td>{{ item.total }}</td>
                    </tr>
                    {% endfor %}
                  </tbody>
                </table>
                <br>
                <p align="left">
                  <div class="left"><b>Notice:</b> The following table shows the number of vulnerable C codes generated by various models using our non-secure prompt dataset. The results demonstrate the number of generated vulnerable codes among the five most probable model outputs. Columns two to five provide details results generating codes for various CWEs. Column six provides the number of found vulnerable codes with the other CWEs that CodeQL queries. The last column provides the sum of all codes with at least one security vulnerability.
                  </div>
                </p>
                <br>
                <table class="table c stripe hover row-border order-column" id="c">
                  <thead>
                    <tr>
                      <th>Model Name</th>
                      <th>CWE-022</th>
                      <th>CWE-190</th>
                      <th>CWE-476</th>
                      <th>CWE-787</th>
                      <th>Other</th>
                      <th>Total</th>
                    </tr>
                  </thead>
                  <tbody>
                    {% for item in site.data.details_c.records %}
                    <tr>
                      <td>{{ item.title }}</td>                      
                      <td>{{ item.cwe_022 }}</td>
                      <td>{{ item.cwe_190 }}</td>
                      <td>{{ item.cwe_476 }}</td>
                      <td>{{ item.cwe_787 }}</td>
                      <td>{{ item.other }}</td>
                      <td>{{ item.total }}</td>
                    </tr>
                    {% endfor %}
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>


  <section class="section" id="BibTeX">
    <div class="container is-max-desktop content">
      <div class="bibtex-body">
        <h2 class="title">BibTeX</h2>
        <pre><code>@inproceedings{
debenedetti2023a,
title={CodeLMSec Benchmark: Systematically Evaluating and Finding Security Vulnerabilities in Black-Box Code Language Models},
author={Hossein Hajipour and Keno Hassler and Thorsten Holz and Lea Schönherr and Mario Fritz},
booktitle={Second IEEE Conference on Secure and Trustworthy Machine Learning},
year={2024}
}</code></pre>
      </div>
    </div>
  </section>


  <footer class="footer">
    <div class="container">
      <div class="columns is-centered">
        <div class="column is-8">
          <div class="content">
            <p>
              This website is adapted from <a href="https://ds1000-code-gen.github.io/">ds1000-code-gen.github.io</a> and <a href="https://infi-coder.github.io/inficoder-eval/">infi-coder.github.io/inficoder-eval</a>, and is licensed under a <a rel="license"
                href="http://creativecommons.org/licenses/by-sa/4.0/">Creative
                Commons Attribution-ShareAlike 4.0 International License</a>.
            </p>
          </div>
        </div>
      </div>
    </div>
  </footer>
  
  <script>
    $(document).ready( function () {
      $('.mainTable').DataTable({ordering: true, order: [[1, 'desc']], columns: [{ "type": "html" },{ "type": "num" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" }]});
    } );

    $(document).ready( function () {
      $('.python').DataTable({ordering: true, order: [[12, 'desc']], columns: [{ "type": "html" },{ "type": "num" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" }, { "type": "num-fmt" }, { "type": "num-fmt" },{ "type": "num-fmt" }], fixedColumns: true, paging: false, scrollCollapse: true, scrollX: true,});
    } );

    $(document).ready( function () {
      $('.c').DataTable({ordering: true, order: [[6, 'desc']], columns: [{ "type": "html" },{ "type": "num" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" }]});
    } );
    
    // new DataTable('.python', {
    // fixedColumns: true,
    // paging: false,
    // scrollCollapse: true,
    // scrollX: true,
    // scrollY: 300,
    // "bDestroy": true
    // });

  </script>

</body>

</html>
