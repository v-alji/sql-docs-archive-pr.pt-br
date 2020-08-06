---
title: MSSQLSERVER_3452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3452 (Database Engine error)
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 662d342064e8094400a6b672e21704877b4d0448
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568604"
---
# <a name="mssqlserver_3452"></a><span data-ttu-id="6e118-102">MSSQLSERVER_3452</span><span class="sxs-lookup"><span data-stu-id="6e118-102">MSSQLSERVER_3452</span></span>
    
## <a name="details"></a><span data-ttu-id="6e118-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="6e118-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e118-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="6e118-104">Product Name</span></span>|<span data-ttu-id="6e118-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6e118-105">SQL Server</span></span>|  
|<span data-ttu-id="6e118-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="6e118-106">Event ID</span></span>|<span data-ttu-id="6e118-107">3452</span><span class="sxs-lookup"><span data-stu-id="6e118-107">3452</span></span>|  
|<span data-ttu-id="6e118-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="6e118-108">Event Source</span></span>|<span data-ttu-id="6e118-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6e118-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6e118-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6e118-110">Component</span></span>|<span data-ttu-id="6e118-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6e118-111">SQLEngine</span></span>|  
|<span data-ttu-id="6e118-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="6e118-112">Symbolic Name</span></span>|<span data-ttu-id="6e118-113">REC_CHECKIDENTITY</span><span class="sxs-lookup"><span data-stu-id="6e118-113">REC_CHECKIDENTITY</span></span>|  
|<span data-ttu-id="6e118-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="6e118-114">Message Text</span></span>|<span data-ttu-id="6e118-115">A recuperação do banco de dados '%.\*ls' (%d) detectou uma possível inconsistência do valor da identidade na ID da tabela %d.</span><span class="sxs-lookup"><span data-stu-id="6e118-115">Recovery of database '%.\*ls' (%d) detected possible identity value inconsistency in table ID %d.</span></span> <span data-ttu-id="6e118-116">Execute DBCC CHECKIDENT ('%.\*ls').</span><span class="sxs-lookup"><span data-stu-id="6e118-116">Run DBCC CHECKIDENT ('%.\*ls').</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6e118-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="6e118-117">Explanation</span></span>  
 <span data-ttu-id="6e118-118">Durante a atualização para o [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], o processo para recuperar os valores de identidade no banco de dados encontrou uma inconsistência nos metadados.</span><span class="sxs-lookup"><span data-stu-id="6e118-118">During the upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the process to recover the identity values in the database found an inconsistency in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6e118-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="6e118-119">User Action</span></span>  
 <span data-ttu-id="6e118-120">Execute DBCC CHECKIDENT.</span><span class="sxs-lookup"><span data-stu-id="6e118-120">Run DBCC CHECKIDENT.</span></span>  
  
  
