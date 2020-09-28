---
title: Jekyll を使用して GitHub Pages サイトにテーマを追加する
intro: テーマを追加およびカスタマイズすることにより、Jekyll サイトをパーソナライズできます。
redirect_from:
  - /articles/customizing-css-and-html-in-your-jekyll-theme/
  - /articles/adding-a-jekyll-theme-to-your-github-pages-site/
  - /articles/adding-a-theme-to-your-github-pages-site-using-jekyll
product: '{{ site.data.reusables.gated-features.pages }}'
versions:
  free-pro-team: '*'
  enterprise-server: '*'
---

リポジトリへの書き込み権限があるユーザは、Jekyll を使用して {{ site.data.variables.product.prodname_pages }} サイトにテーマを追加できます。

{{ site.data.reusables.pages.test-locally }}

### テーマを追加する

{{ site.data.reusables.pages.navigate-site-repo }}
{{ site.data.reusables.pages.navigate-publishing-source }}
2. *_config.yml* に移動します。
{{ site.data.reusables.repositories.edit-file }}
4. テーマ名のために、ファイルに新しい行を追加します。 {% if currentVersion == "free-pro-team@latest" or currentVersion ver_gt "enterprise-server@2.18" %}
   - サポートされている名前を使うには、{% else %}{% endif %}`theme: THEME-NAME` と入力します。_THEME-NAME_ の部分は、テーマのリポジトリの README に表示されている名前に置き換えます。 サポートされているテーマのリストについては、{{ site.data.variables.product.prodname_pages }} サイトで「[サポートされているテーマ](https://pages.github.com/themes/)」を参照してください。 ![Supported theme in config file](/assets/images/help/pages/add-theme-to-config-file.png){% if currentVersion == "free-pro-team@latest" or currentVersion ver_gt "enterprise-server@2.18" %}
   - {{ site.data.variables.product.prodname_dotcom }} にホストされているその他の任意の Jekyll テーマを使うには、`remote_theme: THEME-NAME` と入力します。THEME-NAME の部分は、テーマのリポジトリの README に表示されている名前に置き換えます。 ![Unsupported theme in config file](/assets/images/help/pages/add-remote-theme-to-config-file.png){% endif %}
{{ site.data.reusables.files.write_commit_message }}
{{ site.data.reusables.files.choose-commit-email }}
{{ site.data.reusables.files.choose_commit_branch }}
{{ site.data.reusables.files.propose_file_change }}

### テーマの CSS をカスタマイズする

{{ site.data.reusables.pages.best-with-supported-themes }}

{{ site.data.reusables.pages.theme-customization-help}}

{{ site.data.reusables.pages.navigate-site-repo }}
{{ site.data.reusables.pages.navigate-publishing-source }}
1. _/assets/css/style.scss_ という新しいファイルを作成します。
2. ファイルの先頭に、以下の内容を追加します。
  ```
  ---
  ---

  @import "{{ site.theme }}";
  ```
3. カスタム CSS または Sass (インポートファイルも含む) があれば `@import` 行の直後に追加します。

### テーマの HTML レイアウトをカスタマイズする

{{ site.data.reusables.pages.best-with-supported-themes }}

{{ site.data.reusables.pages.theme-customization-help}}

1. {{ site.data.variables.product.prodname_dotcom }} 上で、テーマのソースリポジトリにアクセスします。 たとえば、Minima のソースリポジトリは https://github.com/jekyll/minima です。
2. *_layouts* フォルダ内で、テーマの _default.html_ ファイルに移動します。
3. ファイルのコンテンツをコピーします。
{{ site.data.reusables.pages.navigate-site-repo }}
{{ site.data.reusables.pages.navigate-publishing-source }}
6. *_layouts/default.html* というファイルを作成します。
7. 先ほどコピーしたデフォルトのレイアウトコンテンツを貼り付けます。
8. 必要に応じてレイアウトをカスタマイズします。

### 参考リンク

- [新しいファイルの作成](/articles/creating-new-files)