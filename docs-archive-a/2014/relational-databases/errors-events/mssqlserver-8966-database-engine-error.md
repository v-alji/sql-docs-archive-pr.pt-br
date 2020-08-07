---
title: MSSQLSERVER_8966 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8966 (Database Engine error)
ms.assetid: 6b1150fd-9dfd-4df9-8f08-8eca237667db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d3a12d5d0732ba8694db3d4c7dcae1eac59d28b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584149"
---
# <a name="mssqlserver_8966"></a><span data-ttu-id="ca504-102">MSSQLSERVER_8966</span><span class="sxs-lookup"><span data-stu-id="ca504-102">MSSQLSERVER_8966</span></span>
    
## <a name="details"></a><span data-ttu-id="ca504-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ca504-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca504-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="ca504-104">Product Name</span></span>|<span data-ttu-id="ca504-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca504-105">SQL Server</span></span>|  
|<span data-ttu-id="ca504-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="ca504-106">Event ID</span></span>|<span data-ttu-id="ca504-107">8966</span><span class="sxs-lookup"><span data-stu-id="ca504-107">8966</span></span>|  
|<span data-ttu-id="ca504-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="ca504-108">Event Source</span></span>|<span data-ttu-id="ca504-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ca504-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ca504-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ca504-110">Component</span></span>|<span data-ttu-id="ca504-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ca504-111">SQLEngine</span></span>|  
|<span data-ttu-id="ca504-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="ca504-112">Symbolic Name</span></span>|<span data-ttu-id="ca504-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span><span class="sxs-lookup"><span data-stu-id="ca504-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span></span>|  
|<span data-ttu-id="ca504-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="ca504-114">Message Text</span></span>|<span data-ttu-id="ca504-115">Não foi possível ler e travar a página P_ID com o tipo de trava TYPE.</span><span class="sxs-lookup"><span data-stu-id="ca504-115">Unable to read and latch page P_ID with latch type TYPE.</span></span> <span data-ttu-id="ca504-116">Falha em OPERATION.</span><span class="sxs-lookup"><span data-stu-id="ca504-116">OPERATION failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ca504-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="ca504-117">Explanation</span></span>  
 <span data-ttu-id="ca504-118">Houve uma falha na leitura da página ou não foi possível usar uma trava em uma página PFS ou GAM.</span><span class="sxs-lookup"><span data-stu-id="ca504-118">The page read failed or a latch could not be taken on a PFS or GAM page.</span></span> <span data-ttu-id="ca504-119">Pode haver um tempo limite de trava ou outras mensagens acompanhantes no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca504-119">There may be latch time-out or other accompanying messages in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ca504-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="ca504-120">User Action</span></span>  
 <span data-ttu-id="ca504-121">Procure essas mensagens no log de erros SQL e corrija os erros.</span><span class="sxs-lookup"><span data-stu-id="ca504-121">Review the SQL error log for accompanying messages and resolve these errors.</span></span>  
  
  
