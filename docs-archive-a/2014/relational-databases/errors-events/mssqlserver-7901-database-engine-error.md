---
title: MSSQLSERVER_7901 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7901 (Database Engine error)
ms.assetid: 2d0d19b9-947b-4474-9ff8-7e03019ab93d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fae6e55cbe7170f795aff85400da2c5cdaef780a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574015"
---
# <a name="mssqlserver_7901"></a><span data-ttu-id="31f5b-102">MSSQLSERVER_7901</span><span class="sxs-lookup"><span data-stu-id="31f5b-102">MSSQLSERVER_7901</span></span>
    
## <a name="details"></a><span data-ttu-id="31f5b-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="31f5b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31f5b-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="31f5b-104">Product Name</span></span>|<span data-ttu-id="31f5b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="31f5b-105">SQL Server</span></span>|  
|<span data-ttu-id="31f5b-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="31f5b-106">Event ID</span></span>|<span data-ttu-id="31f5b-107">7901</span><span class="sxs-lookup"><span data-stu-id="31f5b-107">7901</span></span>|  
|<span data-ttu-id="31f5b-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="31f5b-108">Event Source</span></span>|<span data-ttu-id="31f5b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="31f5b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="31f5b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="31f5b-110">Component</span></span>|<span data-ttu-id="31f5b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="31f5b-111">SQLEngine</span></span>|  
|<span data-ttu-id="31f5b-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="31f5b-112">Symbolic Name</span></span>|<span data-ttu-id="31f5b-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span><span class="sxs-lookup"><span data-stu-id="31f5b-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span></span>|  
|<span data-ttu-id="31f5b-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="31f5b-114">Message Text</span></span>|<span data-ttu-id="31f5b-115">A instrução de correção não foi processada.</span><span class="sxs-lookup"><span data-stu-id="31f5b-115">The repair statement was not processed.</span></span> <span data-ttu-id="31f5b-116">Esse nível de correção não tem suporte quando o banco de dados está no modo de emergência.</span><span class="sxs-lookup"><span data-stu-id="31f5b-116">This level of repair is not supported when the database is in emergency mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="31f5b-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="31f5b-117">Explanation</span></span>  
 <span data-ttu-id="31f5b-118">O banco de dados está no modo de emergência e foi especificado um nível de correção diferente de REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="31f5b-118">The database is in emergency mode and a repair level other than REPAIR_ALLOW_DATA_LOSS has been specified.</span></span> <span data-ttu-id="31f5b-119">Não é possível fazer correções no modo de emergência, a menos que REPAIR_ALLOW_DATA_LOSS seja especificado.</span><span class="sxs-lookup"><span data-stu-id="31f5b-119">Repairs cannot be made in emergency mode unless REPAIR_ALLOW_DATA_LOSS is specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31f5b-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="31f5b-120">User Action</span></span>  
 <span data-ttu-id="31f5b-121">Execute o comando novamente e especifique a opção REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="31f5b-121">Rerun the command and specify the REPAIR_ALLOW_DATA_LOSS option.</span></span>  
  
  
