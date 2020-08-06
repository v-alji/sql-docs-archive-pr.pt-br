---
title: MSSQLSERVER_1461 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1461 (Database Engine error)
ms.assetid: fce10907-4753-441b-b624-f28e00ed7520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6667728b2cc134632ddc538b662d73533ee4d6ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581897"
---
# <a name="mssqlserver_1461"></a><span data-ttu-id="00506-102">MSSQLSERVER_1461</span><span class="sxs-lookup"><span data-stu-id="00506-102">MSSQLSERVER_1461</span></span>
    
## <a name="details"></a><span data-ttu-id="00506-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="00506-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00506-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="00506-104">Product Name</span></span>|<span data-ttu-id="00506-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="00506-105">SQL Server</span></span>|  
|<span data-ttu-id="00506-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="00506-106">Event ID</span></span>|<span data-ttu-id="00506-107">1461</span><span class="sxs-lookup"><span data-stu-id="00506-107">1461</span></span>|  
|<span data-ttu-id="00506-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="00506-108">Event Source</span></span>|<span data-ttu-id="00506-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="00506-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="00506-110">Componente</span><span class="sxs-lookup"><span data-stu-id="00506-110">Component</span></span>|<span data-ttu-id="00506-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="00506-111">SQLEngine</span></span>|  
|<span data-ttu-id="00506-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="00506-112">Symbolic Name</span></span>|<span data-ttu-id="00506-113">DBM_SAFETY_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="00506-113">DBM_SAFETY_MISMATCH</span></span>|  
|<span data-ttu-id="00506-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="00506-114">Message Text</span></span>|<span data-ttu-id="00506-115">Foram detectados níveis de segurança diferentes no espelhamento de banco de dados entre servidores para o banco de dados "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="00506-115">Different database mirroring safety levels among servers were detected for database "%.\*ls".</span></span> <span data-ttu-id="00506-116">O nível de segurança FULL será usado.</span><span class="sxs-lookup"><span data-stu-id="00506-116">The FULL safety level will be used.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00506-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="00506-117">Explanation</span></span>  
 <span data-ttu-id="00506-118">As conexões de espelhamento foram perdidas quando o nível de segurança da transação foi modificado porque as configurações de segurança da transação eram inconsistentes nos bancos de dados principal e espelho.</span><span class="sxs-lookup"><span data-stu-id="00506-118">Mirroring connections were broken when the transaction safety level was modified because the transaction safety settings were inconsistent on the principal and mirror databases.</span></span> <span data-ttu-id="00506-119">A configuração de segurança padrão da segurança da transação completa será usada.</span><span class="sxs-lookup"><span data-stu-id="00506-119">The default safety setting of full-transaction safety will be used.</span></span> <span data-ttu-id="00506-120">A sessão será executada em modo de segurança alta.</span><span class="sxs-lookup"><span data-stu-id="00506-120">The session will run in high-safety mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00506-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="00506-121">User Action</span></span>  
 <span data-ttu-id="00506-122">Para desativar a segurança da transação, execute novamente a instrução ALTER DATABASE *database_name* SET PARTNER SAFETY OFF no banco de dados de entidade.</span><span class="sxs-lookup"><span data-stu-id="00506-122">To set transaction safety off, rerun the ALTER DATABASE *database_name* SET PARTNER SAFETY OFF statement on the principal database.</span></span>  
  
  
