---
title: 'Tutorial: usando a fonte OData [SSIS] | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2c64cf8b-5edb-48df-8ffe-697096258f71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a13b04494ed00251774b490b1cc929769a869acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582023"
---
# <a name="tutorial-using-the-odata-source-ssis"></a><span data-ttu-id="59386-102">Tutorial: Usando o OData Source [SSIS]</span><span class="sxs-lookup"><span data-stu-id="59386-102">Tutorial: Using the OData Source [SSIS]</span></span>
  <span data-ttu-id="59386-103">Este tutorial orienta você pelo processo de extrair a coleção **Funcionários** do serviço **Northwind** OData de amostra (http://services.odata.org/V3/Northwind/Northwind.svc/) e, em seguida, carregue-o para um arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="59386-103">This tutorial walks you through the process to extract the **Employees** collection from the sample **Northwind** OData service (http://services.odata.org/V3/Northwind/Northwind.svc/), and then load it into a flat file.</span></span>  
  
## <a name="1-create-an-integration-services-project"></a><span data-ttu-id="59386-104">1. Criar um projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="59386-104">1. Create an Integration Services Project</span></span>  
  
1.  <span data-ttu-id="59386-105">Inicie o **SQL Server Data Tools** ou o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59386-105">Launch **SQL Server Data Tools** or [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="59386-106">Clique em **Arquivo**, aponte para **Novo** e clique em **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="59386-106">Click **File**, point to **New**, and click **Project**.</span></span>  
  
3.  <span data-ttu-id="59386-107">Na caixa de diálogo **Novo Projeto** , expanda **Instalado**, **Modelos**, **Business Intelligence**e clique em **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="59386-107">In the **New Project** dialog box, expand **Installed**, expand **Templates**, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
4.  <span data-ttu-id="59386-108">Selecione **Projeto do Integration Services** como tipo de projeto.</span><span class="sxs-lookup"><span data-stu-id="59386-108">Select **Integration Services Project** for the type of project.</span></span>  
  
5.  <span data-ttu-id="59386-109">Insira um **nome** e selecione um **local** para o projeto e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="59386-109">Enter a **name** and select a **location** for the project, and click **OK**.</span></span>  
  
## <a name="2-add-and-configure-odata-source-to-the-ssis-package"></a><span data-ttu-id="59386-110">2. Adicionar e configurar OData Source ao pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="59386-110">2. Add and Configure OData Source to the SSIS Package</span></span>  
  
1.  <span data-ttu-id="59386-111">Arraste e solte uma **Tarefa de Fluxo de Dados** da **Caixa de Ferramentas do SSIS** para a superfície de design de fluxo de controle do seu pacote SSIS.</span><span class="sxs-lookup"><span data-stu-id="59386-111">Drag-drop a **Data Flow Task** from the **SSIS Toolbox** on to the control flow design surface of your SSIS package.</span></span>  
  
2.  <span data-ttu-id="59386-112">Clique na guia **Fluxo de Dados** ou clique duas vezes na **Tarefa de Fluxo de Dados** recém-adicionada para iniciar a **superfície de design Fluxo de Dados**.</span><span class="sxs-lookup"><span data-stu-id="59386-112">Click the **Data Flow** tab, or double click on the newly added **Data Flow Task** to launch the **Data Flow design surface**.</span></span>  
  
3.  <span data-ttu-id="59386-113">Arraste e solte o **OData Source** do grupo **Comum** para a **Caixa de Ferramentas do SSIS**.</span><span class="sxs-lookup"><span data-stu-id="59386-113">Drag-drop **OData Source** from the **Common** group in the **SSIS Toolbox**.</span></span> <span data-ttu-id="59386-114">Quando o **OData Source** for instalado pela primeira vez, ele aparecerá sob o grupo **Comum** na **Caixa de Ferramentas do SSIS**.</span><span class="sxs-lookup"><span data-stu-id="59386-114">When the **OData Source** is first installed, it will appear under the **Common** group in the **SSIS Toolbox**.</span></span>  
  
4.  <span data-ttu-id="59386-115">Clique duas vezes no componente **OData Source** para iniciar a caixa de diálogo **Editor do OData Source** .</span><span class="sxs-lookup"><span data-stu-id="59386-115">Double click the **OData Source** component to launch the **OData Source Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="59386-116">Clique em **Novo...** para adicionar um novo Gerenciador de Conexões OData.</span><span class="sxs-lookup"><span data-stu-id="59386-116">Click **New...** to add a new OData Connection Manager.</span></span>  
  
6.  <span data-ttu-id="59386-117">Insira a URL do serviço OData para **Local do documento de serviço**.</span><span class="sxs-lookup"><span data-stu-id="59386-117">Enter the OData service URL for **Service document location**.</span></span> <span data-ttu-id="59386-118">Essa pode ser a URL do documento do serviço ou para um feed ou a uma entidade específica.</span><span class="sxs-lookup"><span data-stu-id="59386-118">This can be the URL to the service document, or to a specific feed or entity.</span></span> <span data-ttu-id="59386-119">Para fins deste tutorial, digite [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/) .</span><span class="sxs-lookup"><span data-stu-id="59386-119">For the purpose of this tutorial, type [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/).</span></span>  
  
7.  <span data-ttu-id="59386-120">Verifique se a **Autenticação do Windows** está selecionada como **autenticação** a ser usada para acessar o serviço OData.</span><span class="sxs-lookup"><span data-stu-id="59386-120">Confirm that **Windows Authentication** is selected for the **authentication** to use to access the OData Service.</span></span> <span data-ttu-id="59386-121">A**Autenticação do Windows** está selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="59386-121">**Windows Authentication** is selected by default.</span></span> <span data-ttu-id="59386-122">Para usar a autenticação básica, selecione **Usar este nome de usuário e senha**.</span><span class="sxs-lookup"><span data-stu-id="59386-122">To use basic authentication, select **Use this user name and password**.</span></span>  
  
8.  <span data-ttu-id="59386-123">Clique em **Testar Conexão** para a conexão e clique em **OK** para criar uma instância do Gerenciador de Conexões OData.</span><span class="sxs-lookup"><span data-stu-id="59386-123">Click **Test Connection** to the connection, and click **OK** to create an instance of OData Connection Manager.</span></span>  
  
9. <span data-ttu-id="59386-124">Na caixa de diálogo **Editor do OData Source** , verifique se a opção **Coleção** está selecionada para **Usar coleção no caminho do recurso** .</span><span class="sxs-lookup"><span data-stu-id="59386-124">In the **OData Source Editor** Dialog Box, confirm that **Collection** is selected for **Use collection on resource path** option.</span></span>  
  
10. <span data-ttu-id="59386-125">Na lista suspensa **Coleção** , selecione **Employees**.</span><span class="sxs-lookup"><span data-stu-id="59386-125">From the **Collection** drop down list, select **Employees**.</span></span>  
  
11. <span data-ttu-id="59386-126">Insira as opções de consulta adicionais do OData ou filtros para **Opções de Consulta**.</span><span class="sxs-lookup"><span data-stu-id="59386-126">Enter any additional OData query options or filters for **Query Options**.</span></span> <span data-ttu-id="59386-127">Ex.:</span><span class="sxs-lookup"><span data-stu-id="59386-127">Ex.</span></span> <span data-ttu-id="59386-128">$orderby=CompanyName&$top=100.</span><span class="sxs-lookup"><span data-stu-id="59386-128">$orderby=CompanyName&$top=100.</span></span> <span data-ttu-id="59386-129">Para este tutorial, insira **$top=5**.</span><span class="sxs-lookup"><span data-stu-id="59386-129">For the purpose of this tutorial, enter **$top=5**.</span></span>  
  
12. <span data-ttu-id="59386-130">Clique em **Visualizar** para visualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="59386-130">Click **Preview** to preview the data.</span></span>  
  
13. <span data-ttu-id="59386-131">Clique em **Colunas** no painel de navegação esquerdo para mudar para a página **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="59386-131">Click **Columns** in the left navigation pane to switch to the **Columns** page.</span></span>  
  
14. <span data-ttu-id="59386-132">Selecione **EmployeeID**, **FirstName**e **LastName** em **Colunas Externas Disponíveis** marcando as caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="59386-132">Select **EmployeeID**, **FirstName**, and **LastName** from **Available External Columns** by checking the check boxes.</span></span>  
  
15. <span data-ttu-id="59386-133">Clique em **OK** para fechar a caixa de diálogo **Editor do OData Source** .</span><span class="sxs-lookup"><span data-stu-id="59386-133">Click **OK** to close the **OData Source Editor** dialog box.</span></span>  
  
## <a name="3-add-flat-file-destination-and-test-the-solution"></a><span data-ttu-id="59386-134">3. Adicionar o destino de arquivo simples e testar a solução</span><span class="sxs-lookup"><span data-stu-id="59386-134">3. Add Flat File Destination and Test the Solution</span></span>  
  
1.  <span data-ttu-id="59386-135">Agora, arraste e solte um **Destino de Arquivo Simples** da **Caixa de Ferramentas do SSIS** para a superfície de design de Fluxo de Dados abaixo do componente **OData Source** .</span><span class="sxs-lookup"><span data-stu-id="59386-135">Now, drag-drop a **Flat File Destination** from **SSIS Toolbox** to the Data Flow design surface below the **OData Source** component.</span></span>  
  
2.  <span data-ttu-id="59386-136">Conecte o componente **OData Source** ao componente **Destino de Arquivo Simples** usando a seta azul.</span><span class="sxs-lookup"><span data-stu-id="59386-136">Connect **OData Source** component with the **Flat File Destination** component using blue arrow.</span></span>  
  
3.  <span data-ttu-id="59386-137">Clique duas vezes em **Destino de Arquivo Simples**.</span><span class="sxs-lookup"><span data-stu-id="59386-137">Double-click on **Flat File Destination**.</span></span> <span data-ttu-id="59386-138">Você deve ver a caixa de diálogo **Editor de Destino de Arquivo Simples** .</span><span class="sxs-lookup"><span data-stu-id="59386-138">You should see the **Flat File Destination Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="59386-139">Na caixa de diálogo **Editor de Destino de Arquivo Simples** , clique em **Novo** para criar um novo gerenciador de conexões de arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="59386-139">In the **Flat File Destination Editor** dialog box, click **New** to create a new flat file connection manager.</span></span>  
  
5.  <span data-ttu-id="59386-140">Na caixa de diálogo **Formato de Arquivo Simples** , selecione **Delimitado**.</span><span class="sxs-lookup"><span data-stu-id="59386-140">In the **Flat File Format** dialog box, select **Delimited**.</span></span> <span data-ttu-id="59386-141">Você deve ver a caixa de diálogo **Editor de Gerenciador de Conexões de Arquivo Simples** .</span><span class="sxs-lookup"><span data-stu-id="59386-141">You should see the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
6.  <span data-ttu-id="59386-142">Na caixa de diálogo **Editor de Gerenciador de Conexões de Arquivo Simples** , como **Nome do Arquivo**, insira **c:\Employees.txt**.</span><span class="sxs-lookup"><span data-stu-id="59386-142">In the **Flat File Connection Manager Editor** dialog box, for the **File name**, enter **c:\Employees.txt**.</span></span>  
  
7.  <span data-ttu-id="59386-143">No painel de navegação esquerdo, clique em **Colunas**.</span><span class="sxs-lookup"><span data-stu-id="59386-143">In the left navigation pane, click **Columns**.</span></span> <span data-ttu-id="59386-144">Você pode visualizar os dados nessa página.</span><span class="sxs-lookup"><span data-stu-id="59386-144">You can preview the data on this page.</span></span>  
  
8.  <span data-ttu-id="59386-145">Clique em OK para fechar a caixa de diálogo **Editor de Gerenciador de Conexões de Arquivo Simples** .</span><span class="sxs-lookup"><span data-stu-id="59386-145">Click OK to close the **Flat File Connection Manager** Editor dialog box.</span></span>  
  
9. <span data-ttu-id="59386-146">Na caixa de diálogo **Editor de Destino de Arquivo Simples** , clique em **Mapeamentos** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="59386-146">In the **Flat File Destination Editor** dialog box, click **Mappings** in the left navigation pane.</span></span> <span data-ttu-id="59386-147">Examine os mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="59386-147">Review the mappings.</span></span>  
  
10. <span data-ttu-id="59386-148">Clique em OK para fechar a caixa de diálogo **Editor de Destino de Arquivo Simples** .</span><span class="sxs-lookup"><span data-stu-id="59386-148">Click OK to close the **Flat File Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="59386-149">Compile e execute o pacote do SSIS.</span><span class="sxs-lookup"><span data-stu-id="59386-149">Compile and execute the SSIS package.</span></span> <span data-ttu-id="59386-150">Verifique se o arquivo de saída foi criado com a ID, o Nome e o Sobrenome de 5 funcionários do feed do OData.</span><span class="sxs-lookup"><span data-stu-id="59386-150">Verify that the output file is created with ID, First Name, and Last Name for 5 employees from the OData feed.</span></span>  
  
  
