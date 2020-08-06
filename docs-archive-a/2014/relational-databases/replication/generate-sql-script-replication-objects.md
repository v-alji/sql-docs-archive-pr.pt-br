---
title: Gerar Script SQL (objetos de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.generatesqlscript.f1
helpviewer_keywords:
- Generate SQL Script dialog box
ms.assetid: b7ccc34e-1c22-44b8-8eb5-f6423af3164e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 31a4b318eb3a4c0e5d9f79f43efdcf97c42957f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569891"
---
# <a name="generate-sql-script-replication-objects"></a><span data-ttu-id="a6e40-102">Gerar Script SQL (objetos de replicação)</span><span class="sxs-lookup"><span data-stu-id="a6e40-102">Generate SQL Script (Replication Objects)</span></span>
  <span data-ttu-id="a6e40-103">Um script de replicação contém os procedimentos armazenados do sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] necessários para implementar os componentes de replicação com scripts, como uma publicação ou assinatura.</span><span class="sxs-lookup"><span data-stu-id="a6e40-103">A replication script contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures necessary to implement the replication components scripted, such as a publication or subscription.</span></span> <span data-ttu-id="a6e40-104">Todos os componentes de replicação em uma topologia devem ser incluídos no script como parte de um plano de recuperação de desastre  e os scripts também podem ser usados para automatizar tarefas repetitivas.</span><span class="sxs-lookup"><span data-stu-id="a6e40-104">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="a6e40-105">A replicação oferece duas caixas de diálogo para scripts de objetos de replicação:</span><span class="sxs-lookup"><span data-stu-id="a6e40-105">Replication offers two dialog boxes for scripting replication objects:</span></span>  
  
-   <span data-ttu-id="a6e40-106">**Gerar Script SQL**, disponível no menu de contexto da pasta **Replicação** e todas as subpastas no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6e40-106">**Generate SQL Script**, which is available from the context menu of the **Replication** folder and all subfolders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a6e40-107">Essa caixa de diálogo permite scripts de todos os objetos de replicação em uma instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6e40-107">This dialog box allows you to script all replication objects on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="a6e40-108">**Gerar Script SQL \<ObjectName>** , disponível no menu de contexto para publicações e assinaturas.</span><span class="sxs-lookup"><span data-stu-id="a6e40-108">**Generate SQL Script \<ObjectName>**, which is available from the context menu for publications and subscriptions.</span></span> <span data-ttu-id="a6e40-109">Essa caixa de diálogo permite script de objetos individuais.</span><span class="sxs-lookup"><span data-stu-id="a6e40-109">This dialog box allows you to script individual objects.</span></span>  
  
 <span data-ttu-id="a6e40-110">Essas caixas de diálogo fazem scripts de objetos em uma instância única do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; elas não conectam com outras instâncias para script de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="a6e40-110">These dialog boxes script objects on a single instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they do not connect to other instances to script related objects.</span></span>  
  
## <a name="generate-sql-script-options"></a><span data-ttu-id="a6e40-111">Opções Generate SQL Script</span><span class="sxs-lookup"><span data-stu-id="a6e40-111">Generate SQL Script Options</span></span>  
 <span data-ttu-id="a6e40-112">**Propriedades do Distribuidor**</span><span class="sxs-lookup"><span data-stu-id="a6e40-112">**Distributor properties**</span></span>  
 <span data-ttu-id="a6e40-113">Selecione para script de procedimentos armazenados para: habilitar ou desabilitar o Distribuidor; adicionar ou descartar Publicadores associados com o Distribuidor e criar ou descartar o banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="a6e40-113">Select to script stored procedures to: enable or disable the Distributor; add or drop Publishers associated with the Distributor; and create or drop the distribution database.</span></span>  
  
 <span data-ttu-id="a6e40-114">**Publicações nestas fontes de dados**</span><span class="sxs-lookup"><span data-stu-id="a6e40-114">**Publications in the following data sources**</span></span>  
 <span data-ttu-id="a6e40-115">Selecione para script de procedimentos armazenados para: habilitar ou desabilitar publicação e criar ou descartar publicações, artigos, assinaturas push e trabalhos de replicação.</span><span class="sxs-lookup"><span data-stu-id="a6e40-115">Select to script stored procedures to: enable or disable publishing; and create or drop publications, articles, push subscriptions, and replication jobs.</span></span>  
  
 <span data-ttu-id="a6e40-116">**Publicações nestas fontes de dados**</span><span class="sxs-lookup"><span data-stu-id="a6e40-116">**Subscriptions in the following data sources**</span></span>  
 <span data-ttu-id="a6e40-117">Selecione para escrever um script de procedimentos armazenados para criar ou descartar assinaturas pull e trabalhos de replicação.</span><span class="sxs-lookup"><span data-stu-id="a6e40-117">Select to script stored procedures to create or drop pull subscriptions and replication jobs.</span></span>  
  
 <span data-ttu-id="a6e40-118">**Criar ou habilitar os componentes** e **Descartar ou desabilitar os componentes**</span><span class="sxs-lookup"><span data-stu-id="a6e40-118">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="a6e40-119">Especifique se o script deve incluir comandos para criação ou remoção de um objeto de replicação.</span><span class="sxs-lookup"><span data-stu-id="a6e40-119">Specify whether the script should include commands for creating or dropping a replication object.</span></span> <span data-ttu-id="a6e40-120">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda usar a caixa de diálogo para criar um conjunto de scripts para habilitar e desabilitar componentes.</span><span class="sxs-lookup"><span data-stu-id="a6e40-120">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you use the dialog box to create a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="a6e40-121">**Trabalhos de replicação**</span><span class="sxs-lookup"><span data-stu-id="a6e40-121">**Replication jobs**</span></span>  
 <span data-ttu-id="a6e40-122">Selecione para script de trabalhos de replicação além de chamadas de procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="a6e40-122">Select to script replication jobs in addition to stored procedure calls.</span></span> <span data-ttu-id="a6e40-123">Essa opção só está disponível ao efetuar script de um Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a6e40-123">This option is available only when scripting from a Distributor.</span></span>  
  
 <span data-ttu-id="a6e40-124">Procedimentos armazenados de replicação criam os trabalhos necessários quando são executados, portanto, não é necessário selecionar essa opção.</span><span class="sxs-lookup"><span data-stu-id="a6e40-124">Replication stored procedures create the necessary jobs when they are executed, so it is not required to select this option.</span></span> <span data-ttu-id="a6e40-125">No entanto, pode ser útil ter um registro dos trabalhos criados, caso seja necessário recriar um trabalho individual.</span><span class="sxs-lookup"><span data-stu-id="a6e40-125">However, it can be useful to have a record of the jobs created in case an individual job must be recreated.</span></span>  
  
## <a name="generate-sql-script-objectname-options"></a><span data-ttu-id="a6e40-126">Opções Gerar Script SQL \<ObjectName></span><span class="sxs-lookup"><span data-stu-id="a6e40-126">Generate SQL Script \<ObjectName> Options</span></span>  
 <span data-ttu-id="a6e40-127">**Criar ou habilitar os componentes** e **Descartar ou desabilitar os componentes**</span><span class="sxs-lookup"><span data-stu-id="a6e40-127">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="a6e40-128">Especifique se o script deve incluir comandos para criação ou remoção de um objeto de replicação.</span><span class="sxs-lookup"><span data-stu-id="a6e40-128">Specify whether the script should include commands for creating or dropping a replication object.</span></span> <span data-ttu-id="a6e40-129">A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda usar a caixa de diálogo para, criando um conjunto de scripts para habilitar e desabilitar componentes.</span><span class="sxs-lookup"><span data-stu-id="a6e40-129">[!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you use the dialog box, creating a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="a6e40-130">**Trabalhos de replicação**</span><span class="sxs-lookup"><span data-stu-id="a6e40-130">**Replication jobs**</span></span>  
 <span data-ttu-id="a6e40-131">Essa opção só está disponível na caixa de diálogo **Gerar Script SQL** .</span><span class="sxs-lookup"><span data-stu-id="a6e40-131">This option is available only from the **Generate SQL Script** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e40-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a6e40-132">See Also</span></span>  
 [<span data-ttu-id="a6e40-133">Replicação de script</span><span class="sxs-lookup"><span data-stu-id="a6e40-133">Scripting Replication</span></span>](scripting-replication.md)  
  
  
