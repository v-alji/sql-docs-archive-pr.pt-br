---
title: Exibir a lista de pacotes no servidor do Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 67a992d1-7524-4f4b-b3d8-ebd9e5ea82a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47b30f9ea0b2abae73f9260b873b7c8436c423eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678273"
---
# <a name="view-the-list-of-packages-on-the-integration-services-server"></a><span data-ttu-id="bb893-102">Exibir a lista de pacotes no servidor do Integration Services</span><span class="sxs-lookup"><span data-stu-id="bb893-102">View the List of Packages on the Integration Services Server</span></span>
  <span data-ttu-id="bb893-103">Você pode exibir a lista de pacotes armazenados no servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] em uma de duas diferentes maneiras.</span><span class="sxs-lookup"><span data-stu-id="bb893-103">You can view the list of packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server in one of two ways.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="bb893-104">acesso</span><span class="sxs-lookup"><span data-stu-id="bb893-104">access</span></span>  
 <span data-ttu-id="bb893-105">Para exibir a lista de pacotes armazenados no servidor, consulte a exibição [catalog.packages &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-views/catalog-packages-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="bb893-105">To view the list of packages that are stored on the server, query the view, [catalog.packages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-packages-ssisdb-database).</span></span>  
  
 <span data-ttu-id="bb893-106">Em [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb893-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>  
 <span data-ttu-id="bb893-107">Para exibir pacotes armazenados no servidor usando o Pesquisador de Objetos no [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], siga o procedimento abaixo.</span><span class="sxs-lookup"><span data-stu-id="bb893-107">To view packages stored on the server by using Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], follow the procedure below.</span></span>  
  
### <a name="to-view-packages-using-ssmanstudiofull"></a><span data-ttu-id="bb893-108">Para exibir pacotes usando o [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb893-108">To view packages using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>  
  
1.  <span data-ttu-id="bb893-109">No [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], conecte-se ao servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb893-109">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="bb893-110">Ou seja, conecte-se à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o banco de dados do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb893-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="bb893-111">Em Pesquisador de Objetos, expanda a árvore para exibir o nó **Catálogos do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="bb893-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="bb893-112">Expanda o nó **Catálogos do Integration Services** para exibir o nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="bb893-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="bb893-113">Expanda o nó **SSISDB** para abrir a lista de uma ou mais pastas.</span><span class="sxs-lookup"><span data-stu-id="bb893-113">Expand the **SSISDB** node to display a list of one or more folders.</span></span> <span data-ttu-id="bb893-114">Cada pasta contém um ou mais projetos na pasta **Projetos** e cada projeto contém um mais pacotes na pasta **Pacotes** .</span><span class="sxs-lookup"><span data-stu-id="bb893-114">Each folder contains one or more projects in the **Projects** folder, and each project contains one more packages in the **Packages** folder.</span></span>  
  
  
