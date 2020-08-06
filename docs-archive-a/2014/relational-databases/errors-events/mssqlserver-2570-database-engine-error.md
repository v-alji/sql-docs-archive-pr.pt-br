---
title: MSSQLSERVER_2570 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 79137d0f70c05c6aa7b758f7e073d152681a14b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679370"
---
# <a name="mssqlserver_2570"></a><span data-ttu-id="11d56-102">MSSQLSERVER_2570</span><span class="sxs-lookup"><span data-stu-id="11d56-102">MSSQLSERVER_2570</span></span>
    
## <a name="details"></a><span data-ttu-id="11d56-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="11d56-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11d56-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="11d56-104">Product Name</span></span>|<span data-ttu-id="11d56-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="11d56-105">SQL Server</span></span>|  
|<span data-ttu-id="11d56-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="11d56-106">Event ID</span></span>|<span data-ttu-id="11d56-107">2570</span><span class="sxs-lookup"><span data-stu-id="11d56-107">2570</span></span>|  
|<span data-ttu-id="11d56-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="11d56-108">Event Source</span></span>|<span data-ttu-id="11d56-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="11d56-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="11d56-110">Componente</span><span class="sxs-lookup"><span data-stu-id="11d56-110">Component</span></span>|<span data-ttu-id="11d56-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="11d56-111">SQLEngine</span></span>|  
|<span data-ttu-id="11d56-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="11d56-112">Symbolic Name</span></span>|<span data-ttu-id="11d56-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="11d56-113">DBCC_COLUMN_VALUE_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="11d56-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="11d56-114">Message Text</span></span>|<span data-ttu-id="11d56-115">Página P_ID, slot S_ID na ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="11d56-115">Page P_ID, slot S_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="11d56-116">O valor de coluna COLUMN_NAME está fora do intervalo para tipo de dados "DATATYPE".</span><span class="sxs-lookup"><span data-stu-id="11d56-116">Column COLUMN_NAME value is out of range for data type "DATATYPE".</span></span> <span data-ttu-id="11d56-117">Atualize a coluna para um valor válido.</span><span class="sxs-lookup"><span data-stu-id="11d56-117">Update column to a legal value.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="11d56-118">Explicação</span><span class="sxs-lookup"><span data-stu-id="11d56-118">Explanation</span></span>  
 <span data-ttu-id="11d56-119">O valor de coluna contido na coluna especificada está fora do intervalo de valores possíveis para o tipo de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="11d56-119">The column value that is contained in the specified column is outside the range of possible values for the column data type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11d56-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="11d56-120">User Action</span></span>  
 <span data-ttu-id="11d56-121">O erro não é reparável.</span><span class="sxs-lookup"><span data-stu-id="11d56-121">The error is not repairable.</span></span> <span data-ttu-id="11d56-122">Atualize a coluna com um valor que esteja dentro do intervalo para o tipo de dados da coluna e execute o comando novamente.</span><span class="sxs-lookup"><span data-stu-id="11d56-122">Update the column to a value within the range for the data type of the column and run the command again.</span></span>  <span data-ttu-id="11d56-123">Para obter mais informações, consulte o artigo [923247](https://support.microsoft.com/kb/923247) da Base de Dados de Conhecimento.</span><span class="sxs-lookup"><span data-stu-id="11d56-123">For more information, see this KB article [923247](https://support.microsoft.com/kb/923247).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d56-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="11d56-124">See Also</span></span>  
 <span data-ttu-id="11d56-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="11d56-125">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 [<span data-ttu-id="11d56-126">Tipos de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="11d56-126">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
