---
title: Caixa de diálogo Procurar Todas as Entidades de Segurança | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.browseprincipals.f1
ms.assetid: f11d2c5e-ee05-45f3-8dc2-0feb99b2f76f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c204411a4daace27745e46269cbcfa0ed33f323f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570189"
---
# <a name="browse-all-principals-dialog-box"></a><span data-ttu-id="f540e-102">Caixa de diálogo Procurar Todas as Entidades de Segurança</span><span class="sxs-lookup"><span data-stu-id="f540e-102">Browse All Principals Dialog Box</span></span>
  <span data-ttu-id="f540e-103">Use a caixa de diálogo **Procurar Todas as Entidades de Segurança** para selecionar uma entidade de segurança de banco de dados para alterar as permissões da entidade de segurança no projeto selecionado ou em todos os projetos contidos em uma pasta selecionada.</span><span class="sxs-lookup"><span data-stu-id="f540e-103">Use the **Browse All Principals** dialog box to select a database principal to change the principal's permissions on the selected project or on all projects contained in a selected folder.</span></span>  
  
 <span data-ttu-id="f540e-104">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="f540e-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="f540e-105">Caixa de diálogo Abrir Todas as Entidades de Segurança</span><span class="sxs-lookup"><span data-stu-id="f540e-105">Open the Browse All Principals dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="f540e-106">Configurar as opções</span><span class="sxs-lookup"><span data-stu-id="f540e-106">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-browse-all-principals-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="f540e-107">Caixa de diálogo Abrir Todas as Entidades de Segurança</span><span class="sxs-lookup"><span data-stu-id="f540e-107">Open the Browse All Principals dialog box</span></span>  
  
1.  <span data-ttu-id="f540e-108">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se ao servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f540e-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="f540e-109">Você está se conectando à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o catálogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="f540e-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB catalog.</span></span>  
  
2.  <span data-ttu-id="f540e-110">Em Pesquisador de Objetos, expanda a árvore para exibir o nó **Catálogos do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="f540e-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="f540e-111">Expanda o nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="f540e-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="f540e-112">Para alteraras permissões da entidade de segurança em todos os projetos contidos em uma pasta selecionada, clique com o botão direito do mouse na pasta e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f540e-112">To change the principal's permissions on all projects contained in a selected folder, right-click the folder and then click **Properties**.</span></span>  
  
     <span data-ttu-id="f540e-113">Para alteraras permissões da entidade de segurança em um projeto selecionado, expanda a pasta que contém o projeto, clique com o botão direito do mouse no projeto e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f540e-113">To change the principal's permissions on a selected project, expand the folder that contains the project, right-click the project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="f540e-114">Selecione a página **Permissões** e clique em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="f540e-114">Select the **Permissions** page, and then click **Browse**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="f540e-115">Configurar as opções</span><span class="sxs-lookup"><span data-stu-id="f540e-115">Configure the Options</span></span>  
 <span data-ttu-id="f540e-116">Esta página exibe as entidades de segurança da exibição do catálogo, sys.database_principals, do banco de dados do SSISDB.</span><span class="sxs-lookup"><span data-stu-id="f540e-116">This page displays the principals from the catalog view, sys.database_principals, of the SSISDB database.</span></span>  
  
 <span data-ttu-id="f540e-117">Ao serem selecionadas, as entidades de segurança serão adicionadas à lista **Logons ou funções** na página **Permissões** da caixa de diálogo pai quando você clicar em **OK** e fechar a caixa de diálogo **Procurar Todas as Entidades de Segurança** .</span><span class="sxs-lookup"><span data-stu-id="f540e-117">Selecting principals adds them to the **Logins or roles** list on the **Permissions** page of the parent dialog box when you click **OK** and close the **Browse All Principals** dialog box.</span></span> <span data-ttu-id="f540e-118">Depois de adicionar entidades de segurança à lista **Logons ou funções** , você poderá alterar as permissões no projeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="f540e-118">After adding principals to the **Logins or roles** list, you can change their permissions on the selected project.</span></span>  
  
 <span data-ttu-id="f540e-119">**Seleção de coluna**</span><span class="sxs-lookup"><span data-stu-id="f540e-119">**Selection column**</span></span>  
 <span data-ttu-id="f540e-120">Selecione para adicionar a entidade de segurança à lista **Logons ou funções** na página **Permissões** da caixa de diálogo pai.</span><span class="sxs-lookup"><span data-stu-id="f540e-120">Select to add the principal to the **Logins or roles** list on the **Permissions** page of the parent dialog box.</span></span>  
  
 <span data-ttu-id="f540e-121">**Coluna de ícone**</span><span class="sxs-lookup"><span data-stu-id="f540e-121">**Icon column**</span></span>  
 <span data-ttu-id="f540e-122">Um ícone que corresponde ao **Tipo** da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="f540e-122">An icon that corresponds to the **Type** of the principal.</span></span>  
  
 <span data-ttu-id="f540e-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f540e-123">**Name**</span></span>  
 <span data-ttu-id="f540e-124">O nome da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="f540e-124">The name of the principal.</span></span>  
  
 <span data-ttu-id="f540e-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f540e-125">**Type**</span></span>  
 <span data-ttu-id="f540e-126">O tipo da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="f540e-126">The type of the principal.</span></span> <span data-ttu-id="f540e-127">Os tipos comuns são:</span><span class="sxs-lookup"><span data-stu-id="f540e-127">The common types are:</span></span>  
  
-   <span data-ttu-id="f540e-128">Usuário do SQL</span><span class="sxs-lookup"><span data-stu-id="f540e-128">SQL User</span></span>  
  
-   <span data-ttu-id="f540e-129">Usuário do Windows</span><span class="sxs-lookup"><span data-stu-id="f540e-129">Windows User</span></span>  
  
-   <span data-ttu-id="f540e-130">Função de banco de dados</span><span class="sxs-lookup"><span data-stu-id="f540e-130">Database Role</span></span>  
  
  
