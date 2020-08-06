---
title: MSSQLSERVER_1793 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 808db1d0-acc1-41d0-9287-8a5455001a02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 54172adb957c3cbc1dbc221d1cae2a583830a1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680450"
---
# <a name="mssqlserver_1793"></a><span data-ttu-id="28cd7-102">MSSQLSERVER_1793</span><span class="sxs-lookup"><span data-stu-id="28cd7-102">MSSQLSERVER_1793</span></span>
    
## <a name="details"></a><span data-ttu-id="28cd7-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="28cd7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28cd7-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="28cd7-104">Product Name</span></span>|<span data-ttu-id="28cd7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="28cd7-105">SQL Server</span></span>|  
|<span data-ttu-id="28cd7-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="28cd7-106">Event ID</span></span>|<span data-ttu-id="28cd7-107">1793</span><span class="sxs-lookup"><span data-stu-id="28cd7-107">1793</span></span>|  
|<span data-ttu-id="28cd7-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="28cd7-108">Event Source</span></span>|<span data-ttu-id="28cd7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="28cd7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="28cd7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="28cd7-110">Component</span></span>|<span data-ttu-id="28cd7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="28cd7-111">SQLEngine</span></span>|  
|<span data-ttu-id="28cd7-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="28cd7-112">Symbolic Name</span></span>|<span data-ttu-id="28cd7-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span><span class="sxs-lookup"><span data-stu-id="28cd7-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span></span>|  
|<span data-ttu-id="28cd7-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="28cd7-114">Message Text</span></span>|<span data-ttu-id="28cd7-115">Não é possível remover o índice '%.\*ls', pois um esquema de partição não está especificado para os dados de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28cd7-115">Cannot drop index '%.\*ls' since a partition scheme is not specified for FILESTREAM data.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28cd7-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="28cd7-116">Explanation</span></span>  
 <span data-ttu-id="28cd7-117">Essa mensagem ocorre quando você tenta remover um índice clusterizado de uma tabela que contém dados FILESTREAM e especifica uma cláusula **MOVE TO** para os dados base, mas não especifica uma cláusula **FILESTREAM_ON** para os dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28cd7-117">This message occurs when you try to drop a clustered index on a table that contains FILESTREAM data, and you specify a **MOVE TO** clause for the base data, but you do not specify a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28cd7-118">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="28cd7-118">User Action</span></span>  
 <span data-ttu-id="28cd7-119">Ao remover um índice clusterizado em uma tabela que contém dados FILESTREAM, use um das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="28cd7-119">When dropping a clustered index on a table that contains FILESTREAM data, use one of the following options:</span></span>  
  
-   <span data-ttu-id="28cd7-120">Especifique uma cláusula **MOVE TO** para os dados base e uma cláusula **FILESTREAM_ON** para os dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28cd7-120">Specify both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
-   <span data-ttu-id="28cd7-121">Não especifique uma cláusula **MOVE TO** para os dados base nem uma cláusula **FILESTREAM_ON** para os dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28cd7-121">Do not specify either a **MOVE TO** clause for the base data or a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
 <span data-ttu-id="28cd7-122">O exemplo a seguir falha porque um esquema de partição foi especificado para os dados básicos, mas não foi especificado para os dados FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="28cd7-122">The following example fails because a partition scheme is specified for the base data, but is not specified for the FILESTREAM data.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY] )  
GO  
```  
  
 <span data-ttu-id="28cd7-123">O exemplo a seguir é bem-sucedido, porque uma cláusula **MOVE TO** para os dados base e uma cláusula **FILESTREAM_ON** para os dados FILESTREAM são especificadas.</span><span class="sxs-lookup"><span data-stu-id="28cd7-123">The following example succeeds because both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data are specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY], filestream_on 'default' )  
GO  
```  
  
 <span data-ttu-id="28cd7-124">O exemplo a seguir também é bem-sucedido, porque uma cláusula **MOVE TO** para os dados base e uma cláusula **FILESTREAM_ON** para os dados FILESTREAM não são especificadas.</span><span class="sxs-lookup"><span data-stu-id="28cd7-124">The following example also succeeds because neither a **MOVE TO** clause for the base data nor a **FILESTREAM_ON** clause for the FILESTREAM data is specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF )  
GO  
```  
  
  
