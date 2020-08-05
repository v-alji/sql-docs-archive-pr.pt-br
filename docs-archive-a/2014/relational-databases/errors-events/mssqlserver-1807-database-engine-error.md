---
title: MSSQLSERVER_1807 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1807 (Database Engine error)
ms.assetid: 13c1b240-098b-4d9e-89aa-21599548e074
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 261d352084e490fb7f9216e1a7e352542e85a6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573083"
---
# <a name="mssqlserver_1807"></a><span data-ttu-id="994a5-102">MSSQLSERVER_1807</span><span class="sxs-lookup"><span data-stu-id="994a5-102">MSSQLSERVER_1807</span></span>
    
## <a name="details"></a><span data-ttu-id="994a5-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="994a5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="994a5-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="994a5-104">Product Name</span></span>|<span data-ttu-id="994a5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="994a5-105">SQL Server</span></span>|  
|<span data-ttu-id="994a5-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="994a5-106">Event ID</span></span>|<span data-ttu-id="994a5-107">1807</span><span class="sxs-lookup"><span data-stu-id="994a5-107">1807</span></span>|  
|<span data-ttu-id="994a5-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="994a5-108">Event Source</span></span>|<span data-ttu-id="994a5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="994a5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="994a5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="994a5-110">Component</span></span>|<span data-ttu-id="994a5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="994a5-111">SQLEngine</span></span>|  
|<span data-ttu-id="994a5-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="994a5-112">Symbolic Name</span></span>|<span data-ttu-id="994a5-113">CANNOT_EX_LOCK</span><span class="sxs-lookup"><span data-stu-id="994a5-113">CANNOT_EX_LOCK</span></span>|  
|<span data-ttu-id="994a5-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="994a5-114">Message Text</span></span>|<span data-ttu-id="994a5-115">Não foi possível obter bloqueio exclusivo no banco de dados '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="994a5-115">Could not obtain exclusive lock on database '%.\*ls'.</span></span> <span data-ttu-id="994a5-116">Tente novamente a operação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="994a5-116">Retry the operation later.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="994a5-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="994a5-117">Explanation</span></span>  
 <span data-ttu-id="994a5-118">Uma operação que exigia acesso exclusivo ao banco de dados não pôde obtê-lo.</span><span class="sxs-lookup"><span data-stu-id="994a5-118">An operation that required exclusive access to the database was unable to obtain it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="994a5-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="994a5-119">User Action</span></span>  
 <span data-ttu-id="994a5-120">Desconecte todas as conexões com esse banco de dados ou tente a consulta novamente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="994a5-120">Disconnect all the connections to that database or try the query again later.</span></span>  
  
  
