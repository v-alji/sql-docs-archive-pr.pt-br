---
title: MSSQLSERVER_5237 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5237 (Database Engine error)
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 224317e290ce15aaed979129733b6273b3b663df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581833"
---
# <a name="mssqlserver_5237"></a><span data-ttu-id="2dffc-102">MSSQLSERVER_5237</span><span class="sxs-lookup"><span data-stu-id="2dffc-102">MSSQLSERVER_5237</span></span>
    
## <a name="details"></a><span data-ttu-id="2dffc-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2dffc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2dffc-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="2dffc-104">Product Name</span></span>|<span data-ttu-id="2dffc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2dffc-105">SQL Server</span></span>|  
|<span data-ttu-id="2dffc-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="2dffc-106">Event ID</span></span>|<span data-ttu-id="2dffc-107">5237</span><span class="sxs-lookup"><span data-stu-id="2dffc-107">5237</span></span>|  
|<span data-ttu-id="2dffc-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="2dffc-108">Event Source</span></span>|<span data-ttu-id="2dffc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2dffc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2dffc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2dffc-110">Component</span></span>|<span data-ttu-id="2dffc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2dffc-111">SQLEngine</span></span>|  
|<span data-ttu-id="2dffc-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="2dffc-112">Symbolic Name</span></span>|<span data-ttu-id="2dffc-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span><span class="sxs-lookup"><span data-stu-id="2dffc-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span></span>|  
|<span data-ttu-id="2dffc-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="2dffc-114">Message Text</span></span>|<span data-ttu-id="2dffc-115">Falha na verificação entre conjuntos de linhas DBCC do objeto 'NAME' (ID de objeto O_ID) devido a um erro de consulta interno.</span><span class="sxs-lookup"><span data-stu-id="2dffc-115">DBCC cross-rowset check failed for object 'NAME' (object ID O_ID) due to an internal query error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2dffc-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="2dffc-116">Explanation</span></span>  
 <span data-ttu-id="2dffc-117">Um erro interno fez com que DBCC não conseguisse executar a consulta para verificar exibições indexadas.</span><span class="sxs-lookup"><span data-stu-id="2dffc-117">An internal error resulted in DBCC not being able to execute the query to check indexed views.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2dffc-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="2dffc-118">User Action</span></span>  
 <span data-ttu-id="2dffc-119">Execute o comando DBCC novamente.</span><span class="sxs-lookup"><span data-stu-id="2dffc-119">Rerun the DBCC command.</span></span>  
  
  
