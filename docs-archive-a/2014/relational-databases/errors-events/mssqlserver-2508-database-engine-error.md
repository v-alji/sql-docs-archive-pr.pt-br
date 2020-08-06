---
title: MSSQLSERVER_2508 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2508 (Database Engine error)
ms.assetid: c37d40e5-c665-4d66-a727-5cb845634fcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11dd1c72c8cae868b7ebcb02e72ef0db81aeafe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680433"
---
# <a name="mssqlserver_2508"></a><span data-ttu-id="545bf-102">MSSQLSERVER_2508</span><span class="sxs-lookup"><span data-stu-id="545bf-102">MSSQLSERVER_2508</span></span>
    
## <a name="details"></a><span data-ttu-id="545bf-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="545bf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="545bf-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="545bf-104">Product Name</span></span>|<span data-ttu-id="545bf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="545bf-105">SQL Server</span></span>|  
|<span data-ttu-id="545bf-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="545bf-106">Event ID</span></span>|<span data-ttu-id="545bf-107">2508</span><span class="sxs-lookup"><span data-stu-id="545bf-107">2508</span></span>|  
|<span data-ttu-id="545bf-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="545bf-108">Event Source</span></span>|<span data-ttu-id="545bf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="545bf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="545bf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="545bf-110">Component</span></span>|<span data-ttu-id="545bf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="545bf-111">SQLEngine</span></span>|  
|<span data-ttu-id="545bf-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="545bf-112">Symbolic Name</span></span>|<span data-ttu-id="545bf-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span><span class="sxs-lookup"><span data-stu-id="545bf-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span></span>|  
|<span data-ttu-id="545bf-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="545bf-114">Message Text</span></span>|<span data-ttu-id="545bf-115">A contagem %.\*ls de objetos "%.\*ls", IDs de índice %d, IDs de partição %I64d e IDs de unidade de alocação %I64d (tipo %.\*ls) está incorreta.</span><span class="sxs-lookup"><span data-stu-id="545bf-115">The %.\*ls count for object "%.\*ls", index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls) is incorrect.</span></span> <span data-ttu-id="545bf-116">Execute DBCC UPDATEUSAGE.</span><span class="sxs-lookup"><span data-stu-id="545bf-116">Run DBCC UPDATEUSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="545bf-117">Explicação</span><span class="sxs-lookup"><span data-stu-id="545bf-117">Explanation</span></span>  
 <span data-ttu-id="545bf-118">Em versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], os valores referentes às contagens de linha de tabela e de índice e as contagens de página podem se tornar incorretas.</span><span class="sxs-lookup"><span data-stu-id="545bf-118">In versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the values for the table and index row counts and page counts can become incorrect.</span></span> <span data-ttu-id="545bf-119">Os bancos de dados criados em versões anteriores ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] podem conter contagens incorretas.</span><span class="sxs-lookup"><span data-stu-id="545bf-119">Databases that were created on versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] may contain incorrect counts.</span></span> <span data-ttu-id="545bf-120">O comando DBCC CHECKDB foi aprimorado para detectar esses erros e retorna essa mensagem de aviso quando detecta o erro.</span><span class="sxs-lookup"><span data-stu-id="545bf-120">DBCC CHECKDB has been enhanced to detect these errors and returns this warning message when the error encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="545bf-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="545bf-121">User Action</span></span>  
 <span data-ttu-id="545bf-122">Execute DBCC UPDATEUSAGE no objeto ou índice especificado ou no banco de dados em que o objeto está contido para corrigir as contagens inválidas.</span><span class="sxs-lookup"><span data-stu-id="545bf-122">Run DBCC UPDATEUSAGE against the specified object or index, or against the database in which the object is contained to correct the invalid counts.</span></span>  
  
  
