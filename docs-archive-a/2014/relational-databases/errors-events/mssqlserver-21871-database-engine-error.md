---
title: MSSQLSERVER_21871 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21871 (Database Engine error)
ms.assetid: d3215378-9282-444f-a18b-00b96fd0133d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f26211da21829a0a898dfb36ff9fefd453c7ad44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680437"
---
# <a name="mssqlserver_21871"></a><span data-ttu-id="8b731-102">MSSQLSERVER_21871</span><span class="sxs-lookup"><span data-stu-id="8b731-102">MSSQLSERVER_21871</span></span>
    
## <a name="details"></a><span data-ttu-id="8b731-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8b731-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b731-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="8b731-104">Product Name</span></span>|<span data-ttu-id="8b731-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b731-105">SQL Server</span></span>|  
|<span data-ttu-id="8b731-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="8b731-106">Event ID</span></span>|<span data-ttu-id="8b731-107">21871</span><span class="sxs-lookup"><span data-stu-id="8b731-107">21871</span></span>|  
|<span data-ttu-id="8b731-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="8b731-108">Event Source</span></span>|<span data-ttu-id="8b731-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8b731-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8b731-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8b731-110">Component</span></span>|<span data-ttu-id="8b731-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8b731-111">SQLEngine</span></span>|  
|<span data-ttu-id="8b731-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="8b731-112">Symbolic Name</span></span>|<span data-ttu-id="8b731-113">SQLErrorNum21871</span><span class="sxs-lookup"><span data-stu-id="8b731-113">SQLErrorNum21871</span></span>|  
|<span data-ttu-id="8b731-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="8b731-114">Message Text</span></span>|<span data-ttu-id="8b731-115">O publicador %s do banco de dados %s não foi redirecionado.</span><span class="sxs-lookup"><span data-stu-id="8b731-115">Publisher %s of database %s has not been redirected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8b731-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="8b731-116">Explanation</span></span>  
 <span data-ttu-id="8b731-117">`sp_validate_replica_hosts_as_publishers`O  verifica a tabela MSredirected_publishers no banco de dados de distribuição à procura de uma entrada para o publicador identificado e o banco de dados publicador.</span><span class="sxs-lookup"><span data-stu-id="8b731-117">`sp_validate_replica_hosts_as_publishers` checks the table MSredirected_publishers in the distribution database for an entry for the identified publisher and publisher database.</span></span>  <span data-ttu-id="8b731-118">`sp_validate_replica_hosts_as_publishers` retorna o erro 21871 quando nenhuma entrada é encontrada.</span><span class="sxs-lookup"><span data-stu-id="8b731-118">`sp_validate_replica_hosts_as_publishers` returns error 21871 when no entry is found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8b731-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="8b731-119">User Action</span></span>  
 <span data-ttu-id="8b731-120">`sp_validate_replica_hosts_as_publishers` só é relevante para publicadores redirecionados.</span><span class="sxs-lookup"><span data-stu-id="8b731-120">`sp_validate_replica_hosts_as_publishers` is only relevant for redirected publishers.</span></span> <span data-ttu-id="8b731-121">Se o banco de dados publicador for membro de um grupo de disponibilidade, use o procedimento armazenado `sp_redirect_publisher` para associar o publicador e o banco de dados publicador com o Nome do Ouvinte do Grupo de Disponibilidade do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="8b731-121">If the publisher database is a member of an availability group, use the stored procedure `sp_redirect_publisher` to associate the publisher and publisher database with the Availability Group Listener Name of the availability group.</span></span>  
  
  
