---
title: MSSQLSERVER_15599 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15599 (Database Engine error)
ms.assetid: 97e427a9-8587-46ea-954b-974b5df9c223
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 15f1b3eb6d97837f1c1c4a9944535cade5b31300
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581891"
---
# <a name="mssqlserver_15599"></a><span data-ttu-id="afc02-102">MSSQLSERVER_15599</span><span class="sxs-lookup"><span data-stu-id="afc02-102">MSSQLSERVER_15599</span></span>
    
## <a name="details"></a><span data-ttu-id="afc02-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="afc02-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="afc02-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="afc02-104">Product Name</span></span>|<span data-ttu-id="afc02-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="afc02-105">SQL Server</span></span>|  
|<span data-ttu-id="afc02-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="afc02-106">Event ID</span></span>|<span data-ttu-id="afc02-107">15599</span><span class="sxs-lookup"><span data-stu-id="afc02-107">15599</span></span>|  
|<span data-ttu-id="afc02-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="afc02-108">Event Source</span></span>|<span data-ttu-id="afc02-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="afc02-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="afc02-110">Componente</span><span class="sxs-lookup"><span data-stu-id="afc02-110">Component</span></span>|<span data-ttu-id="afc02-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="afc02-111">SQLEngine</span></span>|  
|<span data-ttu-id="afc02-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="afc02-112">Symbolic Name</span></span>|<span data-ttu-id="afc02-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span><span class="sxs-lookup"><span data-stu-id="afc02-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span></span>|  
|<span data-ttu-id="afc02-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="afc02-114">Message Text</span></span>|<span data-ttu-id="afc02-115">Auditoria e permissões não podem ser definidas em objetos temporários locais.</span><span class="sxs-lookup"><span data-stu-id="afc02-115">Auditing and permissions can't be set on local temporary objects.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="afc02-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="afc02-116">Explanation</span></span>  
 <span data-ttu-id="afc02-117">Auditoria e permissões não têm nenhum efeito quando definidas para objetos temporários locais ou globais.</span><span class="sxs-lookup"><span data-stu-id="afc02-117">Auditing and permissions do not have any effect when set for local or global temp objects.</span></span> <span data-ttu-id="afc02-118">As instruções não resultam em um erro (as operações retornarão com êxito), mas não têm efeito.</span><span class="sxs-lookup"><span data-stu-id="afc02-118">The statements do not result in an error (the operations will return success), but have no effect.</span></span>  
  
 <span data-ttu-id="afc02-119">Esse comportamento não mudou. No entanto, a partir do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], essa mensagem informativa alerta o usuário.</span><span class="sxs-lookup"><span data-stu-id="afc02-119">This behavior has not changed, however beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this informational message alerts the user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="afc02-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="afc02-120">User Action</span></span>  
 <span data-ttu-id="afc02-121">Nenhuma ação é necessária, mas considere remover as instruções que tentam definir auditoria ou permissões em objetos temporários locais ou globais.</span><span class="sxs-lookup"><span data-stu-id="afc02-121">No action is necessary, but consider removing statements that attempt to set auditing or permissions on local or global temp objects.</span></span>  
  
  
