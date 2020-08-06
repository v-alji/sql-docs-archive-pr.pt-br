---
title: Documentos offline para SQL Server 2014
description: Saiba como instalar a documentação offline para SQL Server 2014. Use o SSMS (SQL Server Management Studio) para exibir o conteúdo offline.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573376"
---
# <a name="install-sql-server-2014-offline-documentation"></a><span data-ttu-id="c1faf-104">Instalar a documentação offline do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c1faf-104">Install SQL Server 2014 offline documentation</span></span>

<span data-ttu-id="c1faf-105">Este artigo descreve como baixar e exibir o conteúdo offline SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="c1faf-105">This article describes how to download and view offline SQL Server 2014 content.</span></span> <span data-ttu-id="c1faf-106">O conteúdo offline permite acessar a documentação sem estar conectado à Internet (embora seja necessário inicialmente uma conexão com a Internet para baixá-lo).</span><span class="sxs-lookup"><span data-stu-id="c1faf-106">Offline content enables you to access the documentation without an internet connection (although an internet connection is initially required to download it).</span></span>

<span data-ttu-id="c1faf-107">A técnica envolve o uso do menu **ajuda** do SQL Server Management Studio (SSMS) para acessar o utilitário Help Viewer (HlpViewer.exe).</span><span class="sxs-lookup"><span data-stu-id="c1faf-107">The technique involves using the **Help** menu of SQL Server Management Studio (SSMS), to access the Help Viewer utility (HlpViewer.exe).</span></span>

<span data-ttu-id="c1faf-108">A documentação offline está disponível para versões do SQL Server no intervalo de 2012-2019 e, talvez, para outras versões posteriores também.</span><span class="sxs-lookup"><span data-stu-id="c1faf-108">Offline documentation is available for versions of SQL Server in the range of 2012-2019, and perhaps for additional later versions too.</span></span> <span data-ttu-id="c1faf-109">Embora você possa ver o conteúdo de [versões anteriores online](https://docs.microsoft.com/previous-versions/sql/), uma opção offline fornece um modo conveniente de acessar conteúdo mais antigo.</span><span class="sxs-lookup"><span data-stu-id="c1faf-109">Although you can view content for [previous versions online](https://docs.microsoft.com/previous-versions/sql/), an offline option provides a convenient way to access the older content.</span></span>

- [<span data-ttu-id="c1faf-110">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c1faf-110">SQL Server 2014</span></span>](#sql-server-2014-offline-content)
- [<span data-ttu-id="c1faf-111">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="c1faf-111">SQL Server 2012</span></span>](#sql-server-2012-offline-content)

<span data-ttu-id="c1faf-112">Para SQL Server 2016 e versões posteriores, consulte a documentação específica da versão para saber como essas versões manipulam a documentação offline.</span><span class="sxs-lookup"><span data-stu-id="c1faf-112">For SQL Server 2016 and later versions, see their version-specific documentation to learn how those versions handle their offline documentation.</span></span>

## <a name="sql-server-2014-offline-content"></a><span data-ttu-id="c1faf-113">Conteúdo offline do SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c1faf-113">SQL Server 2014 offline content</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1faf-114">O conteúdo Transact-SQL do SQL 2014 só está disponível offline.</span><span class="sxs-lookup"><span data-stu-id="c1faf-114">SQL 2014 Transact-SQL content is only available offline.</span></span>

<span data-ttu-id="c1faf-115">As etapas a seguir explicam como carregar conteúdo offline para o SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="c1faf-115">The following steps explain how to load offline content for SQL Server 2014.</span></span>

1. <span data-ttu-id="c1faf-116">Baixe o conteúdo da [Documentação do produto do Microsoft SQL Server 2014 para ambientes restritos por firewall e proxy](https://www.microsoft.com/download/details.aspx?id=42557) no centro de downloads e salve-o em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="c1faf-116">Download the [Product Documentation for Microsoft SQL Server 2014 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=42557) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="c1faf-117">Descompacte o arquivo para exibir o arquivo *. msha* .</span><span class="sxs-lookup"><span data-stu-id="c1faf-117">Unzip the file to view the *.msha* file.</span></span>

   ![Arquivo de instalação da documentação de Ajuda do SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. <span data-ttu-id="c1faf-119">No SSMS, selecione **Adicionar e Remover o Conteúdo da Ajuda** no menu Ajuda.</span><span class="sxs-lookup"><span data-stu-id="c1faf-119">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Adicionar e remover conteúdo do Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="c1faf-121">O Help Viewer é aberto na guia Gerenciar Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c1faf-121">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="c1faf-122">Para instalar o conteúdo de ajuda mais recente, escolha **Disco** em Origem da instalação e selecione as reticências (...).</span><span class="sxs-lookup"><span data-stu-id="c1faf-122">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Gerenciar fonte de disco de conteúdo no Help Viewer](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="c1faf-124">O caminho do repositório Local na guia Gerenciar Conteúdo mostra o local em que o conteúdo será alocado no computador local.</span><span class="sxs-lookup"><span data-stu-id="c1faf-124">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="c1faf-125">Para alterar o local, selecione **Mover**, insira um caminho de pasta diferente no campo **Para** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1faf-125">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="c1faf-126">Se a instalação da ajuda falhar após a alteração do caminho do repositório Local, feche e abra novamente o Help Viewer.</span><span class="sxs-lookup"><span data-stu-id="c1faf-126">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="c1faf-127">Verifique se o novo local consta no caminho do repositório Local e tente realizar a instalação novamente.</span><span class="sxs-lookup"><span data-stu-id="c1faf-127">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="c1faf-128">Localize a pasta onde você descompactou o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c1faf-128">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="c1faf-129">Escolha o arquivo **HelpContentSetup.msha** na pasta e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c1faf-129">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Abrir o arquivo setup.msha do conteúdo da ajuda do SQL Server 2014](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. <span data-ttu-id="c1faf-131">Digite *sql server 2014* na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c1faf-131">Type in *sql server 2014* in the search bar.</span></span> <span data-ttu-id="c1faf-132">Depois de ver o conteúdo de 2014 disponível, selecione **Adicionar** ao lado de cada pacote de conteúdo (manual) que você deseja instalar no Help Viewer e escolha **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="c1faf-132">Once you see the 2014 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Pesquisa de manuais do SQL Server 2014 no Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Atualização e adição de manuais do SQL Server 2014 no Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="c1faf-135">Se o Visualizador da ajuda congelar (travar) ao adicionar conteúdo, altere a linha cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" no arquivo%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings ou HlpViewer_VisualStudiox_en-US. Settings para uma data no futuro.</span><span class="sxs-lookup"><span data-stu-id="c1faf-135">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="c1faf-136">Para obter mais informações sobre esse problema, confira [O Visual Studio Help Viewer congela](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="c1faf-136">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="c1faf-137">Você pode verificar se o conteúdo do SQL Server 2014 foi instalado pesquisando por *sql server 2014* no painel de conteúdo à esquerda.</span><span class="sxs-lookup"><span data-stu-id="c1faf-137">You can verify that the SQL Server 2014 content installed by searching under the content pane on the left for *sql server 2014*.</span></span>

   ![Manuais do SQL Server 2014 atualizados automaticamente](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a><span data-ttu-id="c1faf-139">Conteúdo offline do SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="c1faf-139">SQL Server 2012 offline content</span></span>

<span data-ttu-id="c1faf-140">As etapas a seguir explicam como carregar conteúdo offline para o SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="c1faf-140">The following steps explain how to load offline content for SQL Server 2012</span></span>

1. <span data-ttu-id="c1faf-141">Baixe o conteúdo da [Documentação do produto do Microsoft SQL Server 2012 para ambientes restritos por firewall e proxy](https://www.microsoft.com/download/details.aspx?id=35750) no centro de downloads e salve-o em uma pasta.</span><span class="sxs-lookup"><span data-stu-id="c1faf-141">Download the [Product Documentation for Microsoft SQL Server 2012 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=35750) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="c1faf-142">Descompacte o arquivo para exibir o arquivo *. msha* .</span><span class="sxs-lookup"><span data-stu-id="c1faf-142">Unzip the file to view the *.msha* file.</span></span>

   ![Arquivo de instalação do conteúdo da Ajuda do SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. <span data-ttu-id="c1faf-144">No SSMS, selecione **Adicionar e Remover o Conteúdo da Ajuda** no menu Ajuda.</span><span class="sxs-lookup"><span data-stu-id="c1faf-144">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Adicionar e remover conteúdo do Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="c1faf-146">O Help Viewer é aberto na guia Gerenciar Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c1faf-146">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="c1faf-147">Para instalar o conteúdo de ajuda mais recente, escolha **Disco** em Origem da instalação e selecione as reticências (...).</span><span class="sxs-lookup"><span data-stu-id="c1faf-147">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Gerenciar fonte de disco de conteúdo no Help Viewer](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="c1faf-149">O caminho do repositório Local na guia Gerenciar Conteúdo mostra o local em que o conteúdo será alocado no computador local.</span><span class="sxs-lookup"><span data-stu-id="c1faf-149">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="c1faf-150">Para alterar o local, selecione **Mover**, insira um caminho de pasta diferente no campo **Para** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1faf-150">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="c1faf-151">Se a instalação da ajuda falhar após a alteração do caminho do repositório Local, feche e abra novamente o Help Viewer.</span><span class="sxs-lookup"><span data-stu-id="c1faf-151">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="c1faf-152">Verifique se o novo local consta no caminho do repositório Local e tente realizar a instalação novamente.</span><span class="sxs-lookup"><span data-stu-id="c1faf-152">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="c1faf-153">Localize a pasta onde você descompactou o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c1faf-153">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="c1faf-154">Escolha o arquivo **HelpContentSetup.msha** na pasta e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c1faf-154">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Abrir o arquivo setup.msha do conteúdo da ajuda do SQL Server 2012](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. <span data-ttu-id="c1faf-156">Digite *sql server 2012* na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c1faf-156">Type in *sql server 2012* in the search bar.</span></span> <span data-ttu-id="c1faf-157">Depois de ver o conteúdo de 2012 disponível, selecione **Adicionar** ao lado de cada pacote de conteúdo (manual) que você deseja instalar no Help Viewer e escolha **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="c1faf-157">Once you see the 2012 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Pesquisa de manuais do SQL Server 2012 no Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Atualização e adição de manuais do SQL Server 2012 no Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="c1faf-160">Se o Visualizador da ajuda congelar (travar) ao adicionar conteúdo, altere a linha cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" no arquivo%localappdata%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings ou HlpViewer_VisualStudiox_en-US. Settings para uma data no futuro.</span><span class="sxs-lookup"><span data-stu-id="c1faf-160">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="c1faf-161">Para obter mais informações sobre esse problema, confira [O Visual Studio Help Viewer congela](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="c1faf-161">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="c1faf-162">Você pode verificar se o conteúdo do SQL Server 2012 foi carregado pesquisando por *sql server 2012* no painel de conteúdo à esquerda.</span><span class="sxs-lookup"><span data-stu-id="c1faf-162">You can verify that the SQL Server 2012 content is loaded by searching under the content pane on the left for *sql server 2012*.</span></span>

   ![Documentação do SQL Server 2012 atualizada automaticamente](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a><span data-ttu-id="c1faf-164">Exibir documentação offline</span><span class="sxs-lookup"><span data-stu-id="c1faf-164">View offline documentation</span></span>

<span data-ttu-id="c1faf-165">Você pode exibir SQL Server conteúdo da ajuda usando o menu **ajuda** na versão mais recente do SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="c1faf-165">You can view SQL Server help content using the **HELP** menu in the latest version of SQL Server Management Studio (SSMS).</span></span>

### <a name="view-offline-help-content-in-ssms"></a><span data-ttu-id="c1faf-166">Exibir o conteúdo da ajuda offline no SSMS</span><span class="sxs-lookup"><span data-stu-id="c1faf-166">View offline help content in SSMS</span></span>

<span data-ttu-id="c1faf-167">Para visualizar a ajuda instalada no SSMS, selecione **Inicializar no Help Viewer** no menu Ajuda, para iniciar o Help Viewer.</span><span class="sxs-lookup"><span data-stu-id="c1faf-167">To view the installed help in SSMS, select **Launch in Help Viewer** from the Help menu, to launch the Help Viewer.</span></span>

   ![Inicializar no Help Viewer](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

<span data-ttu-id="c1faf-169">O Help Viewer é aberto na guia Gerenciar Conteúdo, com o sumário da Ajuda instalada no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="c1faf-169">Help Viewer opens to the Manage Content tab, with the installed help table of contents in the left pane.</span></span> <span data-ttu-id="c1faf-170">Selecione os artigos no sumário para exibi-los no painel à direita.</span><span class="sxs-lookup"><span data-stu-id="c1faf-170">select articles in the table of contents to display them in the right pane.</span></span>

> [!Important]
> <span data-ttu-id="c1faf-171">Se o painel de conteúdo não estiver visível, selecione Conteúdos na margem esquerda.</span><span class="sxs-lookup"><span data-stu-id="c1faf-171">If the contents pane is not visible, select Contents on the left margin.</span></span> <span data-ttu-id="c1faf-172">Selecione o ícone de pino para manter o painel de conteúdo aberto.</span><span class="sxs-lookup"><span data-stu-id="c1faf-172">select the pushpin icon to keep the contents pane open.</span></span>  

   ![Help Viewer com conteúdo](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
