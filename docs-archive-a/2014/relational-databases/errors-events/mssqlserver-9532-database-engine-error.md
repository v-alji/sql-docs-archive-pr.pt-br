---
title: MSSQLSERVER_9532 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9532 (Database Engine error)
ms.assetid: ab95cce8-4f97-4aea-a746-a73eea7c9aab
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34ebc7c682d2ffe8bc0205565f5dfd44fdd5b66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573039"
---
# <a name="mssqlserver_9532"></a><span data-ttu-id="a217e-102">MSSQLSERVER_9532</span><span class="sxs-lookup"><span data-stu-id="a217e-102">MSSQLSERVER_9532</span></span>
    
## <a name="details"></a><span data-ttu-id="a217e-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a217e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a217e-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="a217e-104">Product Name</span></span>|<span data-ttu-id="a217e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a217e-105">SQL Server</span></span>|  
|<span data-ttu-id="a217e-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="a217e-106">Event ID</span></span>|<span data-ttu-id="a217e-107">9532</span><span class="sxs-lookup"><span data-stu-id="a217e-107">9532</span></span>|  
|<span data-ttu-id="a217e-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="a217e-108">Event Source</span></span>|<span data-ttu-id="a217e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a217e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a217e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a217e-110">Component</span></span>|<span data-ttu-id="a217e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a217e-111">SQLEngine</span></span>|  
|<span data-ttu-id="a217e-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="a217e-112">Symbolic Name</span></span>|<span data-ttu-id="a217e-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span><span class="sxs-lookup"><span data-stu-id="a217e-113">XMLERR_COLUMNSET_CANNOT_CONVERT_FROM_TO</span></span>|  
|<span data-ttu-id="a217e-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="a217e-114">Message Text</span></span>|<span data-ttu-id="a217e-115">Na operação de consulta/DML envolvendo o conjunto de colunas '%.\*ls', houve falha na conversão ao converter do tipo de dados '%ls' no tipo de dados '%ls' da coluna '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="a217e-115">In the query/DML operation involving  column set '%.\*ls', conversion failed when converting from the data type '%ls' to the data type '%ls' for the column '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a217e-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="a217e-116">Explanation</span></span>  
 <span data-ttu-id="a217e-117">Um conjunto de colunas é uma representação em XML sem-tipo que combina algumas das colunas de uma tabela em uma saída estruturada.</span><span class="sxs-lookup"><span data-stu-id="a217e-117">A column set is an untyped XML representation that combines some of the columns of a table into a structured output.</span></span> <span data-ttu-id="a217e-118">Ao inserir ou atualizar valores de coluna esparsos no conjunto de colunas em XML, os valores inseridos nas colunas esparsas subjacentes são implicitamente convertidos a partir do tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="a217e-118">When you are inserting or updating sparse column values through the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="a217e-119">O valor fornecido não pode ser convertido ao tipo de dados da coluna.</span><span class="sxs-lookup"><span data-stu-id="a217e-119">A value was provided that cannot be converted to the data type of the column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a217e-120">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="a217e-120">User Action</span></span>  
 <span data-ttu-id="a217e-121">Como não foi possível converter implicitamente o valor fornecido, talvez seja uma entrada inválida.</span><span class="sxs-lookup"><span data-stu-id="a217e-121">Because the value provided could not be implicitly converted, it might be an invalid entry.</span></span> <span data-ttu-id="a217e-122">Corrija o erro e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="a217e-122">Correct the error and retry.</span></span> <span data-ttu-id="a217e-123">Se o valor estiver correto, modifique a instrução para usar as colunas individuais em vez do conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="a217e-123">If the value is correct, modify the statement to use the individual columns instead of the column set.</span></span> <span data-ttu-id="a217e-124">Isso permitirá que você converta o valor explicitamente no tipo de dados correto.</span><span class="sxs-lookup"><span data-stu-id="a217e-124">This will allow you to explicitly cast the value into the correct data type.</span></span>  
  
  
