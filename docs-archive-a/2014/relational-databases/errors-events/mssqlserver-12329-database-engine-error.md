---
title: MSSQLSERVER_12329 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12329 (Database Engine error)
ms.assetid: 43f90287-36d5-46c2-ac91-a37202dcf6d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7576e32946ce0a453637273c449bbff20e5b6fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574048"
---
# <a name="mssqlserver_12329"></a><span data-ttu-id="3bfe7-102">MSSQLSERVER_12329</span><span class="sxs-lookup"><span data-stu-id="3bfe7-102">MSSQLSERVER_12329</span></span>
    
## <a name="details"></a><span data-ttu-id="3bfe7-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3bfe7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3bfe7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="3bfe7-104">Product Name</span></span>|<span data-ttu-id="3bfe7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3bfe7-105">SQL Server</span></span>|  
|<span data-ttu-id="3bfe7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="3bfe7-106">Event ID</span></span>|<span data-ttu-id="3bfe7-107">12329</span><span class="sxs-lookup"><span data-stu-id="3bfe7-107">12329</span></span>|  
|<span data-ttu-id="3bfe7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="3bfe7-108">Event Source</span></span>|<span data-ttu-id="3bfe7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3bfe7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3bfe7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3bfe7-110">Component</span></span>|<span data-ttu-id="3bfe7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3bfe7-111">SQLEngine</span></span>|  
|<span data-ttu-id="3bfe7-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="3bfe7-112">Symbolic Name</span></span>|<span data-ttu-id="3bfe7-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="3bfe7-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span></span>|  
|<span data-ttu-id="3bfe7-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="3bfe7-114">Message Text</span></span>|<span data-ttu-id="3bfe7-115">Não há suporte para os tipos de dados char(n) e varchar(n) que usam uma ordenação com uma página de código diferente de 1252 com *construct*.</span><span class="sxs-lookup"><span data-stu-id="3bfe7-115">The data types char(n) and varchar(n) using a collation that has a code page other than 1252 are not supported with  *construct*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3bfe7-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="3bfe7-116">Explanation</span></span>  
 <span data-ttu-id="3bfe7-117">Não use os tipos de dados char(n) e varchar(n) que empreguem uma ordenação com uma página de código diferente de 1252.</span><span class="sxs-lookup"><span data-stu-id="3bfe7-117">Do not use the data types char(n) and varchar(n) using a collation that has a code page other than 1252.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3bfe7-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3bfe7-118">User Action</span></span>  
 <span data-ttu-id="3bfe7-119">Uma situação inesperada que pode gerar esse erro é:</span><span class="sxs-lookup"><span data-stu-id="3bfe7-119">One unexpected situation that can generate this error is:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = 'us_english')  
```  
  
 <span data-ttu-id="3bfe7-120">Use isto:</span><span class="sxs-lookup"><span data-stu-id="3bfe7-120">Use this instead:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
```  
  
  
