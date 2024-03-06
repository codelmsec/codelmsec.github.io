---
layout: mydefault
---

<html>

<head>
  <meta charset="utf-8">
  <meta name="description" content="CodeLMSec Benchmark: Systematically Evaluating and Finding Security Vulnerabilities in Black-Box Code Language Models">
  <meta name="keywords" content="CodeLMSec, code-generation, large-language-model, benchmark">
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
            <!-- <div class="is-size-5 publication-authors">
              <span class="author-block">
              </span>
              <br>
            </div> -->

            <div class="is-size-5 publication-authors">
              <!-- <span class="author-block"><sup>1</sup>Caption of Quận 5, Ho Chi Minh City, Vietnam</span> -->
              <!-- <span class="author-block"><sup>2</sup>Peking University,</span> -->
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
                <!-- Twitter Link. -->
                <!-- <span class="link-block">
                  <a href="https://twitter.com/taoyds/status/1595086401309388801"
                    class="external-link button is-normal is-rounded is-dark">
                    <span class="icon">
                      <i class="fab fa-twitter"></i>
                    </span>
                    <span>Twitter</span>
                  </a>
                </span> -->
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
          <h2 class="title is-3">Overview</h2>
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
                  <div class="left"><b>Notice</b>: we set the max tokens to generate=1024 (since GPT4 generates 662 tokens without the constraint, we provide some wiggle room by setting to 1024 tokens)
                  </div>
                </p>
                <p align="left">
                  <div class="left">We evenly split the 270 benchmark questions to 135-question dev set and 135-question test set. Dev set is publicly available, and the test set is on held where evaluation is available upon request (see below for instructions). 
                  Models are ranked according to full set scores.
                  </div>
                </p>
                <p align="left">
                  <div class="left">For models with >30B parameters, we evaluate once due to resource limit, otherwise we evaluate three times and report the mean and standard deviation.
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
                  <div class="left"><b>Notice</b>: we set the max tokens to generate=1024 (since GPT4 generates 662 tokens without the constraint, we provide some wiggle room by setting to 1024 tokens)
                  </div>
                </p>
                <p align="left">
                  <div class="left">We evenly split the 270 benchmark questions to 135-question dev set and 135-question test set. Dev set is publicly available, and the test set is on held where evaluation is available upon request (see below for instructions). 
                  Models are ranked according to full set scores.
                  </div>
                </p>
                <p align="left">
                  <div class="left">For models with >30B parameters, we evaluate once due to resource limit, otherwise we evaluate three times and report the mean and standard deviation.
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
                      <td>{{ item.top_5_c }}</td>
                      <td>{{ item.top_5_c }}</td>
                      <td>{{ item.top_5_c }}</td>
                      <td>{{ item.top_5_c }}</td>
                      <td>{{ item.top_5_c }}</td>
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
              This website is adapted from <a href="https://ds1000-code-gen.github.io/">ds1000-code-gen.github.io</a> and is licensed under a <a rel="license"
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
      $('.mainTable').DataTable({ordering: true, order: [[3, 'desc']], columns: [{ "type": "html" },{ "type": "num" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" }]});
    } );

    $(document).ready( function () {
      $('.python').DataTable({ordering: true, order: [[3, 'desc']], columns: [{ "type": "html" },{ "type": "num" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" },{ "type": "num-fmt" }], fixedColumns: true, paging: false, scrollCollapse: true, scrollX: true,});
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
