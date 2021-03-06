---
title: 'チュートリアル: Azure Active Directory と Mimecast Personal Portal の統合 | Microsoft Docs'
description: Azure Active Directory と Mimecast Personal Portal の間でシングル サインオンを構成する方法について説明します。
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.reviewer: joflore
ms.assetid: 345b22be-d87e-45a4-b4c0-70a67eaf9bfd
ms.service: active-directory
ms.component: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 04/24/2018
ms.author: jeedes
ms.openlocfilehash: 71ecffebe095fd325837aeb1d6e741a2f3321aea
ms.sourcegitcommit: 1d850f6cae47261eacdb7604a9f17edc6626ae4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39421840"
---
# <a name="tutorial-azure-active-directory-integration-with-mimecast-personal-portal"></a>チュートリアル: Azure Active Directory と Mimecast Personal Portal の統合

このチュートリアルでは、Mimecast Personal Portal と Azure Active Directory (Azure AD) を統合する方法について説明します。

Mimecast Personal Portal と Azure AD の統合には、次の利点があります。

- Mimecast Personal Portal にアクセスする Azure AD ユーザーを制御できます。
- ユーザーが自分の Azure AD アカウントで Mimecast Personal Portal に自動的にサインオン (シングル サインオン) する機能を有効にすることができます。
- 1 つの中央サイト (Azure Portal) でアカウントを管理できます。

SaaS アプリと Azure AD の統合の詳細については、「[Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](../manage-apps/what-is-single-sign-on.md)」をご覧ください。

## <a name="prerequisites"></a>前提条件

Azure AD と Mimecast Personal Portal の統合を構成するには、次のアイテムが必要です。

- Azure AD サブスクリプション
- Mimecast Personal Portal でのシングル サインオンが有効なサブスクリプション

> [!NOTE]
> このチュートリアルの手順をテストする場合、運用環境を使用しないことをお勧めします。

このチュートリアルの手順をテストするには、次の推奨事項に従ってください。

- 必要な場合を除き、運用環境は使用しないでください。
- Azure AD の評価環境がない場合は、[1 か月の評価版を入手できます](https://azure.microsoft.com/pricing/free-trial/)。

## <a name="scenario-description"></a>シナリオの説明
このチュートリアルでは、テスト環境で Azure AD のシングル サインオンをテストします。 このチュートリアルで説明するシナリオは、主に次の 2 つの要素で構成されています。

1. ギャラリーからの Mimecast Personal Portal の追加
1. Azure AD シングル サインオンの構成とテスト

## <a name="adding-mimecast-personal-portal-from-the-gallery"></a>ギャラリーからの Mimecast Personal Portal の追加
Azure AD への Mimecast Personal Portal の統合を構成するには、ギャラリーから管理対象 SaaS アプリの一覧に Mimecast Personal Portal を追加する必要があります。

**ギャラリーから Mimecast Personal Portal を追加するには、次の手順を実行します。**

1. **[Azure Portal](https://portal.azure.com)** の左側のナビゲーション ウィンドウで、**[Azure Active Directory]** アイコンをクリックします。 

    ![Azure Active Directory のボタン][1]

1. **[エンタープライズ アプリケーション]** に移動します。 次に、**[すべてのアプリケーション]** に移動します。

    ![[エンタープライズ アプリケーション] ブレード][2]
    
1. 新しいアプリケーションを追加するには、ダイアログの上部にある **[新しいアプリケーション]** をクリックします。

    ![[新しいアプリケーション] ボタン][3]

1. 検索ボックスに「**Mimecast Personal Portal**」と入力し、結果ウィンドウで **[Mimecast Personal Portal]** を選択し、**[追加]** をクリックして、アプリケーションを追加します。

    ![結果リストの Mimecast Personal Portal](./media/mimecast-personal-portal-tutorial/tutorial_mimecastpersonalportal_addfromgallery.png)

## <a name="configure-and-test-azure-ad-single-sign-on"></a>Azure AD シングル サインオンの構成とテスト

このセクションでは、"Britta Simon" というテスト ユーザーに基づいて、Mimecast Personal Portal で Azure AD のシングル サインオンを構成し、テストします。

シングル サインオンを機能させるには、Azure AD ユーザーに対応する Mimecast Personal Portal ユーザーが Azure AD で認識されている必要があります。 言い換えると、Azure AD ユーザーと Mimecast Personal Portal の関連ユーザーの間で、リンク関係が確立されている必要があります。

Mimecast Personal Portal で Azure AD のシングル サインオンを構成してテストするには、次の手順を完了する必要があります。

1. **[Azure AD シングル サインオンの構成](#configure-azure-ad-single-sign-on)** - ユーザーがこの機能を使用できるようにします。
1. **[Azure AD のテスト ユーザーの作成](#create-an-azure-ad-test-user)** - Britta Simon で Azure AD のシングル サインオンをテストします。
1. **[Mimecast Personal Portal テスト ユーザーの作成](#create-a-mimecast-personal-portal-test-user)** - Mimecast Personal Portal で Britta Simon に対応するユーザーを作成し、Azure AD の Britta Simon にリンクします。
1. **[Azure AD テスト ユーザーの割り当て](#assign-the-azure-ad-test-user)** - Britta Simon が Azure AD シングル サインオンを使用できるようにします。
1. **[シングル サインオンのテスト](#test-single-sign-on)** - 構成が機能するかどうかを確認します。

### <a name="configure-azure-ad-single-sign-on"></a>Azure AD シングル サインオンの構成

このセクションでは、Azure Portal で Azure AD のシングル サインオンを有効にして、Mimecast Personal Portal アプリケーションでシングル サインオンを構成します。

**Mimecast Personal Portal で Azure AD シングル サインオンを構成するには、次の手順に従います。**

1. Azure Portal の **Mimecast Personal Portal** アプリケーション統合ページで、**[シングル サインオン]** をクリックします。

    ![シングル サインオン構成のリンク][4]

1. **[シングル サインオン]** ダイアログで、**[モード]** として **[SAML ベースのサインオン]** を選択し、シングル サインオンを有効にします。
 
    ![[シングル サインオン] ダイアログ ボックス](./media/mimecast-personal-portal-tutorial/tutorial_mimecastpersonalportal_samlbase.png)

1. **[Mimecast Personal Portal のドメインと URL]** セクションで、次の手順を実行します。

    ![[Mimecast Personal Portal のドメインと URL] のシングル サインオン情報](./media/mimecast-personal-portal-tutorial/tutorial_mimecastpersonalportal_url.png)

    a. **[サインオン URL]** ボックスに、次の URL を入力します。 

    | リージョン  |  値 | 
    | --------------- | --------------- | 
    | ヨーロッパ          | `https://eu-api.mimecast.com/login/saml`|
    | 米国   | `https://us-api.mimecast.com/login/saml`|
    | 南アフリカ    | `https://za-api.mimecast.com/login/saml`|
    | オーストラリア       | `https://au-api.mimecast.com/login/saml`|
    | オフショア        | `https://jer-api.mimecast.com/login/saml`|

    b. **[識別子]** ボックスに、次の形式で URL を入力します。

    | リージョン  |  値 | 
    | --------------- | --------------- |
    | ヨーロッパ          | `https://eu-api.mimecast.com/sso/<accountcode>`|
    | 米国   | `https://us-api.mimecast.com/sso/<accountcode>`|    
    | 南アフリカ    | `https://za-api.mimecast.com/sso/<accountcode>`|
    | オーストラリア       | `https://au-api.mimecast.com/sso/<accountcode>`|
    | オフショア        | `https://jer-api.mimecast.com/sso/<accountcode>`|

    c. **[応答 URL]** ボックスに、URL を入力します。 

    | リージョン  |  値 | 
    | --------------- | --------------- | 
    | ヨーロッパ          | `https://eu-api.mimecast.com/login/saml`|
    | 米国   | `https://us-api.mimecast.com/login/saml`|
    | 南アフリカ    | `https://za-api.mimecast.com/login/saml`|
    | オーストラリア       | `https://au-api.mimecast.com/login/saml`|
    | オフショア        | `https://jer-api.mimecast.com/login/saml`|
    
    > [!NOTE] 
    > この識別子の値は実際のものではありません。 この値を実際の識別子で更新してください。 この値を取得するには、[Mimecast Personal Portal クライアント サポート チーム](http://www.mimecast.com/customer-success/technical-support/)にお問い合わせください。 

1. **[SAML 署名証明書]** セクションで、**[証明書 (Base64)]** をクリックし、コンピューターに証明書ファイルを保存します。

    ![証明書のダウンロードのリンク](./media/mimecast-personal-portal-tutorial/tutorial_mimecastpersonalportal_certificate.png) 

1. **[保存]** ボタンをクリックします。

    ![[シングル サインオンの構成] の [保存] ボタン](./media/mimecast-personal-portal-tutorial/tutorial_general_400.png)

1. **[Mimecast Personal Portal 構成]** セクションで **[Mimecast Personal Portal の構成]** をクリックして **[サインオンの構成]** ウィンドウを開きます。 **[クイック リファレンス]** セクションから、**サインアウト URL、SAML エンティティ ID、SAML シングル サインオン サービス URL** をコピーします。

    ![Mimecast Personal Portal の構成](./media/mimecast-personal-portal-tutorial/tutorial_mimecastpersonalportal_configure.png) 

1. 別の Web ブラウザー ウィンドウで、Mimecast Personal Portal の企業サイトに管理者としてログインします。

1. **[サービス] \> [アプリケーション]** に移動します。
   
    ![アプリケーション](./media/mimecast-personal-portal-tutorial/ic794998.png "Applications")

1. **[認証プロファイル]** をクリックします。
   
    ![Authentication Profiles](./media/mimecast-personal-portal-tutorial/ic794999.png "Authentication Profiles")

1. **[新しい認証プロファイル]** をクリックします。
   
    ![新しい認証プロファイル](./media/mimecast-personal-portal-tutorial/ic795000.png "新しい認証プロファイル")

1. **[認証プロバイダー]** セクションで、次の手順に従います。
   
    ![Authentication Profile](./media/mimecast-personal-portal-tutorial/ic795001.png "Authentication Profile")
   
    a. **[説明]** テキストボックスに、構成の名前を入力します。
   
    b. **[Mimecast Personal Portal に SAML 認証を適用]** を選択します。
   
    c. **[プロバイダー]** で **[Azure Active Directory]** を選択します。
   
    d. **[Issuer URL]\(発行者 URL\)** ボックスに、Azure Portal からコピーした **SAML エンティティ ID** の値を貼り付けます。
   
    e. **[Login URL]\(ログイン URL\)** ボックスに、Azure Portal からコピーした **SAML シングル サインオン サービス URL** の値を貼り付けます。
   
    f. **[Logout URL]\(ログアウト URL\)** ボックスに、Azure Portal からコピーした **サインアウト URL** の値を貼り付けます。

    g. Azure Portal からダウンロードした **base-64** でエンコードされた証明書をメモ帳で開き、その内容をクリップボードにコピーして **[Identity Provider Certificate (Metadata)]\(ID プロバイダー証明書 \(メタデータ\)\)** ボックスに貼り付けます。

    h. **[シングル サインオンの許可]** を選択します。
   
    i. **[Save]** をクリックします。

### <a name="create-an-azure-ad-test-user"></a>Azure AD のテスト ユーザーの作成

このセクションの目的は、Azure Portal で Britta Simon というテスト ユーザーを作成することです。

   ![Azure AD のテスト ユーザーの作成][100]

**Azure AD でテスト ユーザーを作成するには、次の手順に従います。**

1. Azure Portal の左側のウィンドウで、**Azure Active Directory** のボタンをクリックします。

    ![Azure Active Directory のボタン](./media/mimecast-personal-portal-tutorial/create_aaduser_01.png)

1. ユーザーの一覧を表示するには、**[ユーザーとグループ]** に移動し、**[すべてのユーザー]** をクリックします。

    ![[ユーザーとグループ] と [すべてのユーザー] リンク](./media/mimecast-personal-portal-tutorial/create_aaduser_02.png)

1. **[ユーザー]** ダイアログ ボックスを開くには、**[すべてのユーザー]** ダイアログ ボックスの上部にある **[追加]** をクリックしてきます。

    ![[追加] ボタン](./media/mimecast-personal-portal-tutorial/create_aaduser_03.png)

1. **[ユーザー]** ダイアログ ボックスで、次の手順に従います。

    ![[ユーザー] ダイアログ ボックス](./media/mimecast-personal-portal-tutorial/create_aaduser_04.png)

    a. **[名前]** ボックスに「**BrittaSimon**」と入力します。

    b. **[ユーザー名]** ボックスに、ユーザーである Britta Simon の電子メール アドレスを入力します。

    c. **[パスワードを表示]** チェック ボックスをオンにし、**[パスワード]** ボックスに表示された値を書き留めます。

    d. **Create** をクリックしてください。
 
### <a name="create-a-mimecast-personal-portal-test-user"></a>Mimecast Personal Portal テスト ユーザーの作成

Azure AD ユーザーが Mimecast Personal Portal にログインできるようにするには、そのユーザーを Mimecast Personal Portal にプロビジョニングする必要があります。 Mimecast Personal Portal の場合、プロビジョニングは手動で行います。

ユーザーを作成する前に、ドメインを登録する必要があります。

**ユーザー プロビジョニングを構成するには、次の手順に従います。**

1. 管理者として **[Mimecast Personal Portal]** にサインオンします。

1. **[ディレクトリ]\>[内部]** に移動します。
   
    ![Directories](./media/mimecast-personal-portal-tutorial/ic795003.png "Directories")

1. **[新規ドメインの登録]** をクリックします。
   
    ![Register New Domain](./media/mimecast-personal-portal-tutorial/ic795004.png "Register New Domain")

1. 新しいドメインを作成したら、 **[新規アドレス]** をクリックします。
   
    ![New Address](./media/mimecast-personal-portal-tutorial/ic795005.png "New Address")

1. 新規アドレス ダイアログで、プロビジョニングする有効な Azure AD アカウントを次の手順で設定します。
   
    ![保存](./media/mimecast-personal-portal-tutorial/ic795006.png "保存")
   
    a. **[Email Address]\(電子メール アドレス\)** ボックスに、ユーザーの**電子メール アドレス**を「**BrittaSimon@contoso.com**」と入力します。
    
    b. **[Global Name]\(グローバル名\)** ボックスに、**ユーザー名**を「**BrittaSimon**」と入力します。

    c. **[Password]\(パスワード\)** および **[Confirm Password]\(確認パスワード\)** ボックスに、ユーザーの**パスワード**を入力します。
   
    b. **[Save]** をクリックします。

>[!NOTE]
>Mimecast Personal Portal から提供されている他の IdeaScale ユーザー アカウント作成ツールや API を使用して、Azure AD ユーザー アカウントをプロビジョニングできます。

### <a name="assign-the-azure-ad-test-user"></a>Azure AD テスト ユーザーの割り当て

このセクションでは、Britta Simon に Mimecast Personal Portal へのアクセスを許可することで、このユーザーが Azure シングル サインオンを使用できるようにします。

![ユーザー ロールを割り当てる][200] 

**Britta Simon を Mimecast Personal Portal に割り当てるには、次の手順に従います。**

1. Azure Portal でアプリケーション ビューを開き、ディレクトリ ビューに移動します。次に、**[エンタープライズ アプリケーション]** に移動し、**[すべてのアプリケーション]** をクリックします。

    ![ユーザーの割り当て][201] 

1. アプリケーションの一覧で **[Mimecast Personal Portal]** を選択します。

    ![アプリケーションの一覧の Mimecast Personal Portal のリンク](./media/mimecast-personal-portal-tutorial/tutorial_mimecastpersonalportal_app.png)  

1. 左側のメニューで **[ユーザーとグループ]** をクリックします。

    ![[ユーザーとグループ] リンク][202]

1. **[追加]** ボタンをクリックします。 次に、**[割り当ての追加]** ダイアログで **[ユーザーとグループ]** を選択します。

    ![[割り当ての追加] ウィンドウ][203]

1. **[ユーザーとグループ]** ダイアログで、ユーザーの一覧から **[Britta Simon]** を選択します。

1. **[ユーザーとグループ]** ダイアログで **[選択]** をクリックします。

1. **[割り当ての追加]** ダイアログで **[割り当て]** ボタンをクリックします。
    
### <a name="test-single-sign-on"></a>シングル サインオンのテスト

このセクションでは、アクセス パネルを使用して Azure AD のシングル サインオン構成をテストします。

アクセス パネルで Mimecast Personal Portal のタイルをクリックすると、Mimecast Personal Portal アプリケーションに自動的にサインオンします。
アクセス パネルの詳細については、[アクセス パネルの概要](../user-help/active-directory-saas-access-panel-introduction.md)に関する記事を参照してください。 

## <a name="additional-resources"></a>その他のリソース

* [SaaS アプリと Azure Active Directory を統合する方法に関するチュートリアルの一覧](tutorial-list.md)
* [Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](../manage-apps/what-is-single-sign-on.md)



<!--Image references-->

[1]: ./media/mimecast-personal-portal-tutorial/tutorial_general_01.png
[2]: ./media/mimecast-personal-portal-tutorial/tutorial_general_02.png
[3]: ./media/mimecast-personal-portal-tutorial/tutorial_general_03.png
[4]: ./media/mimecast-personal-portal-tutorial/tutorial_general_04.png

[100]: ./media/mimecast-personal-portal-tutorial/tutorial_general_100.png

[200]: ./media/mimecast-personal-portal-tutorial/tutorial_general_200.png
[201]: ./media/mimecast-personal-portal-tutorial/tutorial_general_201.png
[202]: ./media/mimecast-personal-portal-tutorial/tutorial_general_202.png
[203]: ./media/mimecast-personal-portal-tutorial/tutorial_general_203.png

