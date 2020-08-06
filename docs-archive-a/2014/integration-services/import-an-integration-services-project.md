---
title: Importar um projeto de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3301c328-b0f5-4517-915c-93713413e453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a98219f3a04d11e086957d64a62e7c64cd51418
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570135"
---
# <a name="import-an-integration-services-project"></a><span data-ttu-id="d09cd-102">Importar um projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="d09cd-102">Import an Integration Services Project</span></span>
  <span data-ttu-id="d09cd-103">Use o **Assistente de Projeto de Importação** do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para criar um projeto de um arquivo de implantação existente (.ispac) ou de um projeto implantado no catálogo do Integration Services.</span><span class="sxs-lookup"><span data-stu-id="d09cd-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]**Import Project Wizard** to create a project from an existing deployment file (.ispac) or from a project deployed to Integration services catalog.</span></span> <span data-ttu-id="d09cd-104">Este recurso é especialmente útil quando você não tiver a cópia original do projeto, mas desejar criar um de um arquivo .ispac ou catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="d09cd-104">This feature is especially useful when you do not have the original copy of the project but you want to create one from an .ispac file or SSISDB catalog.</span></span>  
  
### <a name="to-import-a-project"></a><span data-ttu-id="d09cd-105">Para importar um projeto</span><span class="sxs-lookup"><span data-stu-id="d09cd-105">To Import a Project</span></span>  
  
1.  <span data-ttu-id="d09cd-106">No [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , clique em **novo**  >  **projeto** no menu **arquivo** .</span><span class="sxs-lookup"><span data-stu-id="d09cd-106">In [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New** > **Project** on the **File** menu.</span></span>  
  
2.  <span data-ttu-id="d09cd-107">Na área **Modelos Instalados** da janela **Novo Projeto** , expanda **Business Intelligence**e clique em **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="d09cd-107">In the **Installed Templates** area of the **New Project** window, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="d09cd-108">Selecione **Assistente de Importação de Projeto do Integration Services** da lista de tipos de projetos.</span><span class="sxs-lookup"><span data-stu-id="d09cd-108">Select **Integration Services Import Project Wizard** from the project types list.</span></span>  
  
4.  <span data-ttu-id="d09cd-109">Digite o nome do novo projeto a ser criado na caixa de texto **Nome** .</span><span class="sxs-lookup"><span data-stu-id="d09cd-109">Type a name for the new project to be created in the **Name** text box.</span></span>  
  
5.  <span data-ttu-id="d09cd-110">Digite o caminho ou o local para o projeto na caixa de texto **Localização** ou clique em **Procurar** para selecionar um.</span><span class="sxs-lookup"><span data-stu-id="d09cd-110">Type the path or location for the project in the **Location** text box, or click **Browse** to select one.</span></span>  
  
6.  <span data-ttu-id="d09cd-111">Digite um nome para a solução na caixa de texto **Nome da solução** .</span><span class="sxs-lookup"><span data-stu-id="d09cd-111">Type a name for the solution in the **Solution name** text box.</span></span>  
  
7.  <span data-ttu-id="d09cd-112">Clique em **OK** para iniciar a caixa de diálogo **Assistente de Importação de Projeto do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="d09cd-112">Click **OK** to launch the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
8.  <span data-ttu-id="d09cd-113">Clique em **Avançar** para alternar para a página **Selecionar Origem** .</span><span class="sxs-lookup"><span data-stu-id="d09cd-113">Click **Next** to switch to the **Select Source** page.</span></span>  
  
9. <span data-ttu-id="d09cd-114">Se você estiver importando de um arquivo **.ispac** , digite o caminho incluindo o nome de arquivo na caixa de texto **Caminho** .</span><span class="sxs-lookup"><span data-stu-id="d09cd-114">If you are importing from an **.ispac** file, type the path including file name in the **Path** text box.</span></span> <span data-ttu-id="d09cd-115">Clique em **Procurar** para navegar até a pasta onde você deseja que a solução seja armazenada e digite o nome do arquivo na caixa de texto **Nome de arquivo** e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="d09cd-115">Click **Browse** to navigate to the folder where you want the solution to be stored and type file name in the **File name** text box, and click **Open**.</span></span>  
  
     <span data-ttu-id="d09cd-116">Se você estiver importando de um **Catálogo do Integration Services**, digite o nome da instância de banco de dados na caixa de texto **Nome do servidor** ou clique em **Procurar** e selecione a instância de banco de dados que contém o catálogo.</span><span class="sxs-lookup"><span data-stu-id="d09cd-116">If you are importing from an **Integration Services Catalog**, type the database instance name in the **Server name** text box or click **Browse** and select the database instance that contains the catalog.</span></span>  
  
     <span data-ttu-id="d09cd-117">Clique em **Procurar** ao lado da caixa de texto **Caminho** , expanda a pasta no catálogo, selecione o projeto que você deseja importar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d09cd-117">Click **Browse** next to **Path** text box, expand folder in the catalog, select the project you want to import, and click **OK**.</span></span>  
  
     <span data-ttu-id="d09cd-118">Clique em **Avançar** para alternar para a página **Revisar** .</span><span class="sxs-lookup"><span data-stu-id="d09cd-118">Click **Next** to switch to the **Review** page.</span></span>  
  
10. <span data-ttu-id="d09cd-119">Revise as informações e clique em **Importar** para criar um projeto baseado no projeto existente que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="d09cd-119">Review the information and click **Import** to create a project based on the existing project you selected.</span></span>  
  
11. <span data-ttu-id="d09cd-120">Opcional: clique em **Salvar Relatório** para salvar os resultados em um arquivo</span><span class="sxs-lookup"><span data-stu-id="d09cd-120">Optional: click **Save Report** to save the results to a file</span></span>  
  
12. <span data-ttu-id="d09cd-121">Clique em **Fechar** para fechar a caixa de diálogo **Assistente de Importação de Projeto do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="d09cd-121">Click **Close** to close the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
  
