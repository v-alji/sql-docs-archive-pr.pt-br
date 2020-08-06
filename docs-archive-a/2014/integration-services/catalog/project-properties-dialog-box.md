---
title: Caixa de diálogo Propriedades do Projeto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.general.f1
- sql12.ssis.ssms.isprojectprop.permissions.f1
ms.assetid: d5cf52f5-1fe2-438a-98a3-fe117360acf8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 259ad48f2b1f33356243635bbaa5426a5199eccf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680600"
---
# <a name="project-properties-dialog-box"></a><span data-ttu-id="a12f0-102">Caixa de diálogo Propriedades do Projeto</span><span class="sxs-lookup"><span data-stu-id="a12f0-102">Project Properties Dialog Box</span></span>
  <span data-ttu-id="a12f0-103">Um projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] é uma unidade de implantação.</span><span class="sxs-lookup"><span data-stu-id="a12f0-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project is a unit of deployment.</span></span> <span data-ttu-id="a12f0-104">Cada projeto pode conter pacotes, parâmetros e referências de ambiente.</span><span class="sxs-lookup"><span data-stu-id="a12f0-104">Each project can contain packages, parameters, and environment references.</span></span> <span data-ttu-id="a12f0-105">Um projeto é um objeto protegível e pode definir permissões para principais de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a12f0-105">A project is a securable object and can define permissions for database principals.</span></span> <span data-ttu-id="a12f0-106">Quando um projeto é reimplantado, a versão anterior dele pode ser armazenada no catálogo do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a12f0-106">When a project is re-deployed, the previous version of the project can be stored in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
 <span data-ttu-id="a12f0-107">Os parâmetros de projeto e de pacote podem ser usados para atribuir valores às propriedades nos pacotes em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="a12f0-107">Project parameters and package parameters can be used to assign values to properties within packages at the time of execution.</span></span> <span data-ttu-id="a12f0-108">Alguns parâmetros exigem valores antes da execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="a12f0-108">Some parameters require values before the package can be executed.</span></span> <span data-ttu-id="a12f0-109">Valores de parâmetros que referenciam variáveis de ambiente requerem que o projeto tenha a referência de ambiente correspondente antes da execução.</span><span class="sxs-lookup"><span data-stu-id="a12f0-109">Parameter values that reference environment variables require that the project has the corresponding environment reference prior to execution.</span></span>  
  
 <span data-ttu-id="a12f0-110">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="a12f0-110">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="a12f0-111">Abra a caixa de diálogo Propriedades do Projeto</span><span class="sxs-lookup"><span data-stu-id="a12f0-111">Open the Project Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="a12f0-112">Definir as opções na página Geral</span><span class="sxs-lookup"><span data-stu-id="a12f0-112">Set the options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="a12f0-113">Defina as opções na página Permissões</span><span class="sxs-lookup"><span data-stu-id="a12f0-113">Set the options on the Permissions page</span></span>](#permissions)  
  
##  <a name="open-the-project-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="a12f0-114">Abra a caixa de diálogo Propriedades do Projeto</span><span class="sxs-lookup"><span data-stu-id="a12f0-114">Open the Project Properties dialog box</span></span>  
  
1.  <span data-ttu-id="a12f0-115">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se ao servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a12f0-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="a12f0-116">Você está se conectando à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o banco de dados SSISDB.</span><span class="sxs-lookup"><span data-stu-id="a12f0-116">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="a12f0-117">Em Pesquisador de Objetos, expanda a árvore para exibir o nó **Catálogos do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="a12f0-117">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="a12f0-118">Expanda o nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="a12f0-118">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="a12f0-119">Expanda a pasta que contém o projeto para o qual você deseja definir propriedades.</span><span class="sxs-lookup"><span data-stu-id="a12f0-119">Expand the folder that contains the project that you want to set properties for.</span></span>  
  
5.  <span data-ttu-id="a12f0-120">Clique com o botão direito do mouse no projeto e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="a12f0-120">Right-click the project, and then click **Properties**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="a12f0-121">Definir as opções na página Geral</span><span class="sxs-lookup"><span data-stu-id="a12f0-121">Set the options on the General page</span></span>  
 <span data-ttu-id="a12f0-122">Use a página Geral para exibir as propriedades do projeto.</span><span class="sxs-lookup"><span data-stu-id="a12f0-122">Use the General page to view project properties.</span></span>  
  
 <span data-ttu-id="a12f0-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a12f0-123">**Name**</span></span>  
 <span data-ttu-id="a12f0-124">Lista o nome do projeto.</span><span class="sxs-lookup"><span data-stu-id="a12f0-124">Lists the project name.</span></span>  
  
 <span data-ttu-id="a12f0-125">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="a12f0-125">**Identifier**</span></span>  
 <span data-ttu-id="a12f0-126">Lista a ID do projeto.</span><span class="sxs-lookup"><span data-stu-id="a12f0-126">Lists the project ID.</span></span>  
  
 <span data-ttu-id="a12f0-127">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a12f0-127">**Description**</span></span>  
 <span data-ttu-id="a12f0-128">Exibe a descrição opcional do projeto.</span><span class="sxs-lookup"><span data-stu-id="a12f0-128">Displays the optional description of the project.</span></span>  
  
 <span data-ttu-id="a12f0-129">**Versão do projeto**</span><span class="sxs-lookup"><span data-stu-id="a12f0-129">**Project Version**</span></span>  
 <span data-ttu-id="a12f0-130">Lista a versão do projeto.</span><span class="sxs-lookup"><span data-stu-id="a12f0-130">Lists the project version.</span></span>  
  
 <span data-ttu-id="a12f0-131">**Data de implantação**</span><span class="sxs-lookup"><span data-stu-id="a12f0-131">**Deployment Date**</span></span>  
 <span data-ttu-id="a12f0-132">Lista a data e a hora em que o projeto foi implantado ou reimplantado.</span><span class="sxs-lookup"><span data-stu-id="a12f0-132">Lists the date and time the project was deployed or redeployed.</span></span>  
  
##  <a name="set-the-options-on-the-permissions-page"></a><a name="permissions"></a> <span data-ttu-id="a12f0-133">Defina as opções na página Permissões</span><span class="sxs-lookup"><span data-stu-id="a12f0-133">Set the options on the Permissions page</span></span>  
 <span data-ttu-id="a12f0-134">Use a página **Permissões** para exibir e definir as permissões explícitas para o projeto.</span><span class="sxs-lookup"><span data-stu-id="a12f0-134">Use the **Permissions** page to view and set explicit permissions for the project.</span></span>  
  
 <span data-ttu-id="a12f0-135">Procurar</span><span class="sxs-lookup"><span data-stu-id="a12f0-135">Browse</span></span>  
 <span data-ttu-id="a12f0-136">Clique em **Procurar** para selecionar usuários e funções para os quais você quer definir permissões, usando a caixa de diálogo **Procurar Todas as Entidades de Segurança** .</span><span class="sxs-lookup"><span data-stu-id="a12f0-136">Click **Browse** to select users and roles that you want to set permissions for, by using the **Browse All Principals** dialog box.</span></span>  
  
 <span data-ttu-id="a12f0-137">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a12f0-137">**Name**</span></span>  
 <span data-ttu-id="a12f0-138">Lista o nome do usuário ou função.</span><span class="sxs-lookup"><span data-stu-id="a12f0-138">Lists the name of the user or role.</span></span>  
  
 <span data-ttu-id="a12f0-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a12f0-139">**Type**</span></span>  
 <span data-ttu-id="a12f0-140">Lista o tipo de usuário ou função.</span><span class="sxs-lookup"><span data-stu-id="a12f0-140">Lists the type of user or role.</span></span>  
  
 <span data-ttu-id="a12f0-141">**Permissão**</span><span class="sxs-lookup"><span data-stu-id="a12f0-141">**Permission**</span></span>  
 <span data-ttu-id="a12f0-142">Lista as permissões.</span><span class="sxs-lookup"><span data-stu-id="a12f0-142">Lists the permissions.</span></span>  
  
 <span data-ttu-id="a12f0-143">**Concessor**</span><span class="sxs-lookup"><span data-stu-id="a12f0-143">**Grantor**</span></span>  
 <span data-ttu-id="a12f0-144">Lista o usuário ou função que concede a permissão.</span><span class="sxs-lookup"><span data-stu-id="a12f0-144">Lists the user or role that grants the permission.</span></span>  
  
 <span data-ttu-id="a12f0-145">**Conceder**</span><span class="sxs-lookup"><span data-stu-id="a12f0-145">**Grant**</span></span>  
 <span data-ttu-id="a12f0-146">Quando **Conceder** está selecionado, a permissão é concedida para o usuário ou função selecionado.</span><span class="sxs-lookup"><span data-stu-id="a12f0-146">When **Grant** is selected, the permission is granted for the selected user or role.</span></span>  
  
 <span data-ttu-id="a12f0-147">**Deny**</span><span class="sxs-lookup"><span data-stu-id="a12f0-147">**Deny**</span></span>  
 <span data-ttu-id="a12f0-148">Quando **Negar** está selecionado, a permissão é negada para o usuário ou função selecionado.</span><span class="sxs-lookup"><span data-stu-id="a12f0-148">When **Deny** is selected, the permission is denied for the selected user or role.</span></span>  
  
  
