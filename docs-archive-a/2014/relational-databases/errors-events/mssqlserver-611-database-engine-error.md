---
title: MSSQLSERVER_611 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 611 (Database Engine error)
ms.assetid: ac6a213f-5c38-44ad-bc85-a62863786614
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0caa1c218e8b80059c0c97aac652da7db870af3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583098"
---
# <a name="mssqlserver_611"></a><span data-ttu-id="b7ecc-102">MSSQLSERVER_611</span><span class="sxs-lookup"><span data-stu-id="b7ecc-102">MSSQLSERVER_611</span></span>
    
## <a name="details"></a><span data-ttu-id="b7ecc-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b7ecc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7ecc-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="b7ecc-104">Product Name</span></span>|<span data-ttu-id="b7ecc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7ecc-105">SQL Server</span></span>|  
|<span data-ttu-id="b7ecc-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="b7ecc-106">Event ID</span></span>|<span data-ttu-id="b7ecc-107">611</span><span class="sxs-lookup"><span data-stu-id="b7ecc-107">611</span></span>|  
|<span data-ttu-id="b7ecc-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="b7ecc-108">Event Source</span></span>|<span data-ttu-id="b7ecc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b7ecc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b7ecc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b7ecc-110">Component</span></span>|<span data-ttu-id="b7ecc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b7ecc-111">SQLEngine</span></span>|  
|<span data-ttu-id="b7ecc-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="b7ecc-112">Symbolic Name</span></span>|<span data-ttu-id="b7ecc-113">VAR_SIZE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="b7ecc-113">VAR_SIZE_TOO_BIG</span></span>|  
|<span data-ttu-id="b7ecc-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="b7ecc-114">Message Text</span></span>|<span data-ttu-id="b7ecc-115">Não é possível inserir ou atualizar uma linha porque o tamanho total da coluna variável, incluindo a sobrecarga, está %d bytes acima do limite.</span><span class="sxs-lookup"><span data-stu-id="b7ecc-115">Cannot insert or update a row because total variable column size, including overhead, is %d bytes more than the limit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b7ecc-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="b7ecc-116">Explanation</span></span>  
 <span data-ttu-id="b7ecc-117">O tamanho máximo da coluna variável é maior que o permitido pelo esquema.</span><span class="sxs-lookup"><span data-stu-id="b7ecc-117">The maximum variable column size is more than that allowed by the schema.</span></span> <span data-ttu-id="b7ecc-118">O erro 611 é retornado quando a coluna variável está acima do limite no caso fixo quando o formato de armazenamento vardecimal está habilitado ou quando o tamanho da coluna variável está acima do limite permitido no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para um registro de dados compactado.</span><span class="sxs-lookup"><span data-stu-id="b7ecc-118">Error 611 is returned when the variable column is over the limit in the fixed case when vardecimal storage format is enabled, or when the variable column size is over the limit allowed in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for a compressed data record.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b7ecc-119">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="b7ecc-119">User Action</span></span>  
 <span data-ttu-id="b7ecc-120">Reduza o tamanho do registro.</span><span class="sxs-lookup"><span data-stu-id="b7ecc-120">Reduce the size of the record.</span></span>  
  
  
