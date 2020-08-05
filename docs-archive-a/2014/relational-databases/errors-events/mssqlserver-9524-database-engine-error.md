---
title: MSSQLSERVER_9524 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9524 (Database Engine error)
ms.assetid: 12da7931-e124-4466-889c-046f1b7b7bfd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6c46ee0ef0bd1be299614e2cb04a3d6cd99d92e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573041"
---
# <a name="mssqlserver_9524"></a><span data-ttu-id="69510-102">MSSQLSERVER_9524</span><span class="sxs-lookup"><span data-stu-id="69510-102">MSSQLSERVER_9524</span></span>
    
## <a name="details"></a><span data-ttu-id="69510-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="69510-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69510-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="69510-104">Product Name</span></span>|<span data-ttu-id="69510-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="69510-105">SQL Server</span></span>|  
|<span data-ttu-id="69510-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="69510-106">Event ID</span></span>|<span data-ttu-id="69510-107">9254</span><span class="sxs-lookup"><span data-stu-id="69510-107">9254</span></span>|  
|<span data-ttu-id="69510-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="69510-108">Event Source</span></span>|<span data-ttu-id="69510-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="69510-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="69510-110">Componente</span><span class="sxs-lookup"><span data-stu-id="69510-110">Component</span></span>|<span data-ttu-id="69510-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="69510-111">SQLEngine</span></span>|  
|<span data-ttu-id="69510-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="69510-112">Symbolic Name</span></span>|<span data-ttu-id="69510-113">XMLERR_INVALID_COLUMNSET_XML</span><span class="sxs-lookup"><span data-stu-id="69510-113">XMLERR_INVALID_COLUMNSET_XML</span></span>|  
|<span data-ttu-id="69510-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="69510-114">Message Text</span></span>|<span data-ttu-id="69510-115">O conteúdo XML fornecido não se adapta ao formato XML exigido para conjuntos de colunas esparsos.</span><span class="sxs-lookup"><span data-stu-id="69510-115">The XML content provided does not conform to the required XML format for sparse column sets.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="69510-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="69510-116">Explanation</span></span>  
 <span data-ttu-id="69510-117">Uma tentativa foi feita para modificar um conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="69510-117">An attempt was made to modify a column set.</span></span> <span data-ttu-id="69510-118">É necessário que o conteúdo em XML de um conjunto de colunas esteja de acordo com as restrições de formato de um conjunto de colunas.</span><span class="sxs-lookup"><span data-stu-id="69510-118">The XML content of a column set must meet the format restrictions of a column set.</span></span> <span data-ttu-id="69510-119">O formato geral de um conjunto de colunas é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="69510-119">The general format of a column set is as follows:</span></span>  
  
 `<column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...`  
  
 <span data-ttu-id="69510-120">Para obter mais informações sobre conjuntos de colunas, consulte o tópico "Usando conjuntos de colunas" nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69510-120">For more information about column sets, see the topic "Using Column Sets" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="69510-121">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="69510-121">User Action</span></span>  
 <span data-ttu-id="69510-122">Corrija o formato do XML para o conjunto de colunas na instrução.</span><span class="sxs-lookup"><span data-stu-id="69510-122">Correct the format of the XML for the column set in the statement.</span></span>  
  
  
