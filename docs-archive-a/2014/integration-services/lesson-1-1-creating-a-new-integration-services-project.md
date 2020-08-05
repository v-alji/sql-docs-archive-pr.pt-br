---
title: 'Etapa 1: Criar um novo projeto do Integration Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f14521b5-941e-443b-8f5e-385f98e37fbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d6d16d7febcdecb01eb7a93167c2a18d225a9c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574150"
---
# <a name="step-1-creating-a-new-integration-services-project"></a><span data-ttu-id="762df-102">Etapa 1: Criar um novo projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="762df-102">Step 1: Creating a New Integration Services Project</span></span>
  <span data-ttu-id="762df-103">A primeira etapa na criação de um pacote em [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] é criar um projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="762df-103">The first step in creating a package in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is to create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="762df-104">Esse projeto inclui modelos para objetos – fontes de dados, exibições de fontes de dados e pacotes – usados em uma solução de transformação.</span><span class="sxs-lookup"><span data-stu-id="762df-104">This project includes the templates for the objects - data sources, data source views, and packages - that you use in a data transformation solution.</span></span>  
  
 <span data-ttu-id="762df-105">Os pacotes que serão criados neste tutorial do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] interpretam os valores de dados com distinção de localidade.</span><span class="sxs-lookup"><span data-stu-id="762df-105">The packages that you will create in this [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial interpret the values of locale-sensitive data.</span></span> <span data-ttu-id="762df-106">Se o seu computador não estiver configurado para usar a opção regional Inglês (Estados Unidos), será preciso definir propriedades adicionais no pacote.</span><span class="sxs-lookup"><span data-stu-id="762df-106">If your computer is not configured to use the regional option English (United States), you need to set additional properties in the package.</span></span> <span data-ttu-id="762df-107">Os pacotes usados nas lições 2 a 5 serão copiados a partir do pacote criado na lição 1 e não será preciso atualizar as propriedades que fazem distinção de localidade nos pacotes copiados.</span><span class="sxs-lookup"><span data-stu-id="762df-107">The packages that you use in lessons 2 through 5 are copied from the package created in lesson 1, and you need not update locale-sensitive properties in the copied packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="762df-108">Este tutorial requer o Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="762df-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
>   
>  <span data-ttu-id="762df-109">Para obter mais informações sobre como instalar o SQL Server Data Tools, consulte [Download do SQL Server Data Tools](https://msdn.microsoft.com/data/hh297027).</span><span class="sxs-lookup"><span data-stu-id="762df-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://msdn.microsoft.com/data/hh297027).</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="762df-110">Para criar um novo projeto Integration Services</span><span class="sxs-lookup"><span data-stu-id="762df-110">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="762df-111">Clique no menu **Iniciar** , aponte para **Todos os Programas**, aponte para **Microsoft SQL Server**e clique em **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="762df-111">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, and click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="762df-112">No menu **Arquivo** , aponte para **Novo**e clique em **Projeto** para criar um novo projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="762df-112">On the **File** menu, point to **New**, and click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="762df-113">Na caixa de diálogo **Novo Projeto** , expanda o nó **Business Intelligence** em **Modelos Instalados**e selecione **Projeto do Integration Services** no painel **Modelos** .</span><span class="sxs-lookup"><span data-stu-id="762df-113">In the **New Project** dialog box, expand the **Business Intelligence** node under **Installed Templates**, and select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="762df-114">Na caixa **Nome** , altere o nome padrão para **Tutorial SSIS**.</span><span class="sxs-lookup"><span data-stu-id="762df-114">In the **Name** box, change the default name to **SSIS Tutorial**.</span></span> <span data-ttu-id="762df-115">Opcionalmente, desmarque a caixa de seleção **Criar diretório para a solução** .</span><span class="sxs-lookup"><span data-stu-id="762df-115">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="762df-116">Aceite o local padrão ou clique em **Procurar** para procurar a pasta que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="762df-116">Accept the default location, or click **Browse** to browse to locate the folder you want to use.</span></span> <span data-ttu-id="762df-117">Na caixa de diálogo **Local do Projeto** , clique na pasta e clique em **Selecionar Pasta**.</span><span class="sxs-lookup"><span data-stu-id="762df-117">In the **Project Location** dialog box, click the folder and click **Select Folder**.</span></span>  
  
6.  <span data-ttu-id="762df-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="762df-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="762df-119">Por padrão, um pacote vazio chamado **Package.dtsx**será criado e adicionado ao projeto nos Pacotes do SSIS.</span><span class="sxs-lookup"><span data-stu-id="762df-119">By default, an empty package, titled **Package.dtsx**, will be created and added to your project under SSIS Packages.</span></span>  
  
7.  <span data-ttu-id="762df-120">Na barra de ferramentas do **Gerenciador de Soluções** , clique com o botão direito do mouse em **Package.dtsx**, clique em **Renomear**e renomeie o pacote padrão como **Lesson 1.dtsx**.</span><span class="sxs-lookup"><span data-stu-id="762df-120">In **Solution Explorer** toolbar, right-click **Package.dtsx**, click **Rename**, and rename the default package to **Lesson 1.dtsx**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="762df-121">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="762df-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="762df-122">Etapa 2: Adicionar e configurar um gerenciador de conexões de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="762df-122">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
  
