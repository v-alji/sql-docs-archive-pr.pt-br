---
title: Caixa de diálogo Versões do Projeto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.versions.f1
ms.assetid: a48a387c-2e70-45bc-be2e-26e57a9bb2c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 998dd194c2a056121fd6f7a404e75c7080b85aa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683647"
---
# <a name="project-versions-dialog-box"></a><span data-ttu-id="cdff0-102">Caixa de diálogo Versões do Projeto</span><span class="sxs-lookup"><span data-stu-id="cdff0-102">Project Versions Dialog Box</span></span>
  <span data-ttu-id="cdff0-103">Use a caixa de diálogo **Versões de Projeto** para exibir versões de um projeto e restaurar uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="cdff0-103">Use the **Project Versions** dialog box to view versions of a project and to restore a previous version.</span></span>  
  
 <span data-ttu-id="cdff0-104">Você também pode exibir versões anteriores na exibição [catalog.object_versions &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) e usar o procedimento armazenado [catalog.restore_project &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) para restaurar as versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="cdff0-104">You can also view previous versions in the [catalog.object_versions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) view, and use the [catalog.restore_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) stored procedure to restore previous versions.</span></span>  
  
 <span data-ttu-id="cdff0-105">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="cdff0-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="cdff0-106">Abrir a caixa de diálogo Versões de Projeto</span><span class="sxs-lookup"><span data-stu-id="cdff0-106">Open the Project Versions dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="cdff0-107">Restaurar uma versão do projeto</span><span class="sxs-lookup"><span data-stu-id="cdff0-107">Restore a Project Version</span></span>](#restore)  
  
##  <a name="open-the-project-versions-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="cdff0-108">Abrir a caixa de diálogo Versões de Projeto</span><span class="sxs-lookup"><span data-stu-id="cdff0-108">Open the Project Versions dialog box</span></span>  
  
1.  <span data-ttu-id="cdff0-109">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se ao servidor do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cdff0-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="cdff0-110">Ou seja, conecte-se à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o banco de dados do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cdff0-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="cdff0-111">Em Pesquisador de Objetos, expanda a árvore para exibir o nó **Catálogos do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="cdff0-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="cdff0-112">Expanda o nó **Catálogos do Integration Services** para exibir o nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="cdff0-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="cdff0-113">O nó do **SSISDB** contém uma ou mais pastas e cada uma contém um ou mais projetos.</span><span class="sxs-lookup"><span data-stu-id="cdff0-113">The **SSISDB** node contains one or more folders that each contain one or more projects.</span></span> <span data-ttu-id="cdff0-114">Expanda a pasta que contém o projeto ao qual você está interessado.</span><span class="sxs-lookup"><span data-stu-id="cdff0-114">Expand the folder that contains the project you are interested in.</span></span>  
  
5.  <span data-ttu-id="cdff0-115">Clique com o botão direito do mouse no projeto e clique em **Versões**.</span><span class="sxs-lookup"><span data-stu-id="cdff0-115">Right-click the project, and then click **Versions**.</span></span>  
  
 <span data-ttu-id="cdff0-116">Na caixa de diálogo **Versões do Projeto** , a tabela **Versões** exibe a lista de versões do projeto que foram implantadas no servidor, com a data e a hora em que a versão foi implantada, a data e a hora em que a versão foi restaurada (se tiver sido restaurada), a descrição de versão e um identificador de versão.</span><span class="sxs-lookup"><span data-stu-id="cdff0-116">In the **Project Versions** dialog box, the **Versions** table displays the list of versions of the project that have been deployed on the server, with the date and time the version was deployed, the date and time the version was restored (if it was restored), the version description, and a version identifier.</span></span> <span data-ttu-id="cdff0-117">A versão ativa no momento é indicada com uma marca de seleção na coluna **Atual** da tabela.</span><span class="sxs-lookup"><span data-stu-id="cdff0-117">The currently active version is indicated with a check mark in the **Current** column of the table.</span></span>  
  
##  <a name="restore-a-project-version"></a><a name="restore"></a> <span data-ttu-id="cdff0-118">Restaurar uma versão do projeto</span><span class="sxs-lookup"><span data-stu-id="cdff0-118">Restore a Project Version</span></span>  
 <span data-ttu-id="cdff0-119">Para restaurar uma versão anterior de um projeto, selecione a versão na tabela **Versões** e clique em **Restaurar para Versão Selecionada**.</span><span class="sxs-lookup"><span data-stu-id="cdff0-119">To restore a previous version of a project, select the version in the **Versions** table, and then click **Restore to Selected Version**.</span></span> <span data-ttu-id="cdff0-120">O projeto é restaurado para a versão selecionada e essa versão é indicada com uma marca de seleção na coluna **Atual** da tabela **Versões** .</span><span class="sxs-lookup"><span data-stu-id="cdff0-120">The project is restored to the selected version and that version is indicated with a check mark in the **Current** column of the **Versions** table.</span></span>  
  
  
