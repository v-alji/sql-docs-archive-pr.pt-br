---
title: Métodos de autorização | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], reports
- authorization [Reporting Services]
- reports [Reporting Services], security
- tasks [Reporting Services]
- roles [Reporting Services], methods
ms.assetid: 45e9cf2c-facf-4801-9482-c855403f42a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b04a21b5075e939a4732e2f8ec219e169f4ba440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683403"
---
# <a name="authorization-methods"></a><span data-ttu-id="55fdb-102">Métodos de autorização</span><span class="sxs-lookup"><span data-stu-id="55fdb-102">Authorization Methods</span></span>
  <span data-ttu-id="55fdb-103">Você pode usar estes métodos para gerenciar tarefas, funções e políticas no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="55fdb-103">You can use these methods to manage tasks, roles, and policies on the report server.</span></span>  
  
|<span data-ttu-id="55fdb-104">Método</span><span class="sxs-lookup"><span data-stu-id="55fdb-104">Method</span></span>|<span data-ttu-id="55fdb-105">Ação</span><span class="sxs-lookup"><span data-stu-id="55fdb-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateRole%2A>|<span data-ttu-id="55fdb-106">Adiciona uma nova função ao banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="55fdb-106">Adds a new role to the report server database.</span></span> <span data-ttu-id="55fdb-107">Esse método aplica-se apenas ao modo nativo.</span><span class="sxs-lookup"><span data-stu-id="55fdb-107">This method =applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteRole%2A>|<span data-ttu-id="55fdb-108">Exclui uma função do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="55fdb-108">Deletes a role from the report server database.</span></span> <span data-ttu-id="55fdb-109">Esse método aplica-se somente ao modo nativo.</span><span class="sxs-lookup"><span data-stu-id="55fdb-109">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPermissions%2A>|<span data-ttu-id="55fdb-110">Retorna as permissões de usuário associadas a um item específico no banco de dados do servidor de relatório ou na biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="55fdb-110">Returns the user permissions that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPolicies%2A>|<span data-ttu-id="55fdb-111">Retorna as políticas associadas a um item específico no banco de dados do servidor de relatório ou na biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="55fdb-111">Returns the policies that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetRoleProperties%2A>|<span data-ttu-id="55fdb-112">Retorna propriedades de metadados de função e uma coleção de tarefas associadas.</span><span class="sxs-lookup"><span data-stu-id="55fdb-112">Returns role metadata properties and a collection of associated tasks.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPermissions%2A>|<span data-ttu-id="55fdb-113">Retorna as permissões de sistema do usuário.</span><span class="sxs-lookup"><span data-stu-id="55fdb-113">Returns the user's system permissions.</span></span> <span data-ttu-id="55fdb-114">Esse método aplica-se somente ao modo nativo.</span><span class="sxs-lookup"><span data-stu-id="55fdb-114">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPolicies%2A>|<span data-ttu-id="55fdb-115">Retorna as políticas do sistema, incluindo grupos e funções aos quais elas estão associadas.</span><span class="sxs-lookup"><span data-stu-id="55fdb-115">Returns the system policies, including groups and roles with which they are associated.</span></span> <span data-ttu-id="55fdb-116">Esse método aplica-se somente ao modo nativo.</span><span class="sxs-lookup"><span data-stu-id="55fdb-116">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.InheritParentSecurity%2A>|<span data-ttu-id="55fdb-117">Exclui as políticas associadas a um item específico no banco de dados do servidor de relatório e define as políticas de segurança do item como as do respectivo pai.</span><span class="sxs-lookup"><span data-stu-id="55fdb-117">Deletes the policies that are associated with a particular item in the report server database and sets the security policies for the item to those of its parent.</span></span>|  
|<xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>|<span data-ttu-id="55fdb-118">Retorna um valor booliano que indica se o protocolo SSL é exigido para usar o ponto de extremidade <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="55fdb-118">Returns a Boolean value that indicates whether the Secure Socket Layer (SSL) protocol is required to use the <xref:ReportService2010> end point.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListRoles%2A>|<span data-ttu-id="55fdb-119">Retorna os nomes e as descrições das funções gerenciadas pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="55fdb-119">Returns the names and descriptions of roles that are managed by the report server.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A>|<span data-ttu-id="55fdb-120">Retorna uma lista de métodos SOAP no ponto de extremidade <xref:ReportExecution2005> que exigem uma conexão segura quando invocados.</span><span class="sxs-lookup"><span data-stu-id="55fdb-120">Returns a list of Simple Object Access Protocol (SOAP) methods in the <xref:ReportExecution2005> endpoint that require a secure connection when invoked.</span></span> <span data-ttu-id="55fdb-121">A configuração de `SecureConnectionLevel` do servidor de relatório é usada para determinar quais métodos são retornados.</span><span class="sxs-lookup"><span data-stu-id="55fdb-121">The `SecureConnectionLevel` setting of the report server is used to determine which methods are returned.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListTasks%2A>|<span data-ttu-id="55fdb-122">Retorna as tarefas gerenciadas pelo servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="55fdb-122">Returns the tasks that are managed by the report server.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetPolicies%2A>|<span data-ttu-id="55fdb-123">Define as políticas associadas a um item especificado.</span><span class="sxs-lookup"><span data-stu-id="55fdb-123">Sets the policies that are associated with a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetRoleProperties%2A>|<span data-ttu-id="55fdb-124">Define propriedades de metadados de função e associa um conjunto de tarefas a uma função.</span><span class="sxs-lookup"><span data-stu-id="55fdb-124">Sets role metadata properties and associates a set of tasks with a role.</span></span> <span data-ttu-id="55fdb-125">Esse método aplica-se somente ao modo nativo.</span><span class="sxs-lookup"><span data-stu-id="55fdb-125">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A>|<span data-ttu-id="55fdb-126">Define a política do sistema que define grupos e as funções associadas a eles.</span><span class="sxs-lookup"><span data-stu-id="55fdb-126">Sets the system policy that defines groups and their associated roles.</span></span> <span data-ttu-id="55fdb-127">Esse método aplica-se somente ao modo nativo.</span><span class="sxs-lookup"><span data-stu-id="55fdb-127">This method applies to native mode only.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55fdb-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="55fdb-128">See Also</span></span>  
 <span data-ttu-id="55fdb-129">[Criando aplicativos usando o serviço Web e o .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="55fdb-129">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="55fdb-130">[Serviço Web Servidor de Relatórios](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="55fdb-130">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="55fdb-131">[Métodos do serviço Web Servidor de Relatórios](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="55fdb-131">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="55fdb-132">Referência técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="55fdb-132">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
