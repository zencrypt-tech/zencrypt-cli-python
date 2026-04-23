<!--
*****************************************************************************************
Title: Zencrypt CLI Python Readme ********************************************************
Developed by: Ryan Hatch / Zencrypt Tech *************************************************
Dev Date: Aug 10th 2022 ******************************************************************
Last Updated: 2026 ************************************************************************
Version: 3.0 ******************************************************************************
*****************************************************************************************
-->

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body>
    <br>
    <h1 align="center">Zencrypt CLI Python</h1>
    <p align="center">
      <strong>By: Ryan Hatch / Zencrypt Tech</strong>
      <br>
      <em>Keeping It Simple and Secure.</em>
    </p>
    <p align="center">
      <a href="#overview">Overview</a> •
      <a href="#features">Features</a> •
      <a href="#requirements">Requirements</a> •
      <a href="#installation">Installation</a> •
      <a href="#usage">Usage</a> •
      <a href="#cryptography-notes">Cryptography Notes</a> •
      <a href="#building-an-executable">Build</a> •
      <a href="#contributing">Contributing</a> •
      <a href="#disclaimer">Disclaimer</a> •
      <a href="#license">License</a>
    </p>
    <hr>
    <p align="center">
      &copy; 2026 Ryan Hatch / Zencrypt Tech
      <br>
      All Rights Reserved.
    </p>
    <br>
    <h2 id="overview">Overview</h2>
    <p>
      Zencrypt CLI Python is a terminal-based encryption and hashing tool from the
      Zencrypt Tech project family.
    </p>
    <p>
      This CLI is designed to provide a simple local interface for generating and
      verifying SHA-256 hashes, encrypting and decrypting text, encrypting and
      decrypting files, and testing basic RSA message encryption workflows.
    </p>
    <p>
      This repository is the Python CLI version of Zencrypt. It is intended for
      learning, experimentation, and local encryption workflows.
    </p>
    <hr>
    <h2 id="features">Features</h2>
    <ul>
      <li>
        <strong>Hash generation</strong> using the SHA-256 hashing algorithm with
        an optional salt value.
      </li>
      <li>
        <strong>Hash verification</strong> by comparing provided text and salt
        input against a known hash.
      </li>
      <li>
        <strong>Encrypt and decrypt text</strong> using Fernet symmetric encryption.
      </li>
      <li>
        <strong>Encrypt and decrypt files</strong> with password-derived AES encryption.
      </li>
      <li>
        <strong>RSA message encryption</strong> using RSA-OAEP through Python's
        <code>cryptography</code> library.
      </li>
      <li>
        <strong>Public key export and import</strong> for RSA public keys.
      </li>
      <li>
        <strong>Copy output</strong> to the clipboard.
      </li>
      <li>
        <strong>Clear content</strong> from the clipboard.
      </li>
    </ul>
    <hr>
    <h2 id="requirements">Requirements</h2>
    <p>
      Python 3.10+ is recommended.
    </p>
    <p>
      Required runtime packages:
    </p>
    <pre><code>cryptography
pyperclip</code></pre>
    <p>
      Recommended <code>requirements.txt</code>:
    </p>
    <pre><code>cryptography&gt;=41.0.4
pyperclip&gt;=1.8.2</code></pre>
    <p>
      If you build a Windows executable with PyInstaller, keep that dependency
      separate in <code>requirements-dev.txt</code>.
    </p>
    <p>
      Recommended <code>requirements-dev.txt</code>:
    </p>
    <pre><code>pyinstaller&gt;=6.0.0</code></pre>
    <hr>
    <h2 id="installation">Installation</h2>
    <p>
      To install Zencrypt CLI Python, you will need Python and pip installed on
      your system.
    </p>
    <ol>
      <li>
        Clone the repository:
        <pre><code>git clone https://github.com/zencrypt-tech/zencrypt-cli-python.git</code></pre>
      </li>
      <li>
        Navigate into the project folder:
        <pre><code>cd zencrypt-cli-python</code></pre>
      </li>
      <li>
        Optional but recommended: create a virtual environment.
        <br>
        <br>
        Windows PowerShell:
        <pre><code>python -m venv .venv
.\.venv\Scripts\Activate.ps1</code></pre>
        macOS/Linux:
        <pre><code>python3 -m venv .venv
source .venv/bin/activate</code></pre>
      </li>
      <li>
        Install the required dependencies:
        <pre><code>pip install -r requirements.txt</code></pre>
      </li>
    </ol>
    <hr>
    <h2 id="usage">Usage</h2>
    <p>
      Run the application with:
    </p>
    <pre><code>python zencrypt.py</code></pre>
    <p>
      Follow the on-screen prompts to perform the desired operation.
    </p>
    <h3>Main Menu</h3>
    <pre><code>1 | Hash Manager
2 | Encrypt Text
3 | Encrypt Files
4 | PGP/RSA Encryption
5 | Clear Clipboard
6 | Exit</code></pre>
    <hr>
    <h2 id="cryptography-notes">Cryptography Notes</h2>
    <p>
      This project is a learning-focused CLI and should be treated as a local
      utility, not a production-grade security product.
    </p>
    <ul>
      <li>
        Text encryption uses Fernet symmetric encryption.
      </li>
      <li>
        File encryption uses password-derived AES encryption.
      </li>
      <li>
        RSA message encryption uses RSA-OAEP through Python's
        <code>cryptography</code> library.
      </li>
      <li>
        The RSA feature is not full OpenPGP compatibility, even if older project
        text refers to it as PGP.
      </li>
      <li>
        Local key files should be protected and excluded from version control.
      </li>
    </ul>
    <h3>Planned Improvements</h3>
    <ul>
      <li>AES-GCM or Fernet-based authenticated file encryption.</li>
      <li>Better key management.</li>
      <li>Cleaner import and export workflows.</li>
      <li>Dedicated tests.</li>
      <li>Packaged releases through GitHub Releases instead of committed executables.</li>
    </ul>
    <hr>
    <h2 id="project-structure">Suggested Project Structure</h2>
    <pre><code>zencrypt-cli-python/
├── README.md
├── LICENSE
├── requirements.txt
├── requirements-dev.txt
├── .gitignore
└── zencrypt.py</code></pre>
    <hr>
    <h2 id="building-an-executable">Building an Executable</h2>
    <p>
      If PyInstaller is installed through <code>requirements-dev.txt</code>, you
      can build a local executable with:
    </p>
    <pre><code>pyinstaller --onefile zencrypt.py</code></pre>
    <p>
      Build output should remain local and should not be committed to the source
      repository.
    </p>
    <p>
      If you want to distribute an executable, attach it to a GitHub Release
      instead.
    </p>
    <hr>
    <h2 id="contributing">Contributing</h2>
    <p align="center">
      <strong>
        Please reach out to verify and validate ideas and contributions before
        continuing any further. Although contributions may be welcome, they should
        stay focused on the Python CLI version of Zencrypt.
      </strong>
    </p>
    <p>
      Recommended workflow:
    </p>
    <ol>
      <li>
        Fork the repository.
      </li>
      <li>
        Create a new branch:
        <pre><code>git checkout -b feature/your-feature-name</code></pre>
      </li>
      <li>
        Make your changes.
      </li>
      <li>
        Confirm that no keys, secrets, generated files, executables, or local test
        files are included.
      </li>
      <li>
        Commit your changes:
        <pre><code>git commit -m "Add your feature"</code></pre>
      </li>
      <li>
        Push to the branch:
        <pre><code>git push origin feature/your-feature-name</code></pre>
      </li>
      <li>
        Open a pull request.
      </li>
    </ol>
    <hr>
    <h1 align="center" id="disclaimer">Disclaimer</h1>
    <p align="center">
      <strong>
        <code>&lt;=&gt; &lt;=&gt; &lt;=&gt; &lt;=&gt; &lt;=&gt; &lt;=&gt; &lt;=&gt;</code>
      </strong>
    </p>
    <p align="center">
      <strong>
        <code>
          This script is provided for educational and demonstration purposes only.
          Use it responsibly and only on files, messages, and systems that you own
          or are authorized to work with.
        </code>
      </strong>
    </p>
    <p align="center">
      <strong>
        <code>
          The project maintainer is not responsible for data loss, misuse, damage,
          or improper use of this software.
        </code>
      </strong>
    </p>
    <p align="center">
      <strong>
        <code>&lt;=&gt; &lt;=&gt; &lt;=&gt; &lt;=&gt; &lt;=&gt; &lt;=&gt; &lt;=&gt;</code>
      </strong>
    </p>
    <hr>
    <h2 id="license">License</h2>
    <p>
      This software is the property of the copyright holder and is protected by
      copyright laws. All rights are reserved by the copyright holder unless explicitly granted in writing.
    </p>
    <p>
      The copyright holder grants no implied or express license for the use,
      copying, modification, distribution, or reproduction of this software, in
      whole or in part, without prior written permission from the copyright holder,
      unless a separate license file states otherwise.
    </p>
    <p>
      Any unauthorized use, copying, modification, distribution, or reproduction of
      this software, in whole or in part, is strictly prohibited and may constitute
      a violation of copyright law.
    </p>
    <p align="center">
      <strong>
        <code>
          By using this software, you acknowledge that you have read and understood
          the terms of this license and agree to comply with all applicable laws.
        </code>
      </strong>
    </p>
    <hr>
    <h2 id="contact">Contact</h2>
    <p>
      For inquiries, suggestions, or project-related questions, contact the project
      maintainer through the Zencrypt Tech organization or open a GitHub issue.
    </p>
    <br>
    <p align="center">
      <strong>Zencrypt Tech</strong>
      <br>
      <em>Keeping It Simple and Secure.</em>
    </p>
  </body>
</html>
