---
title: MSSQLSERVER_511 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 511 (Database Engine error)
ms.assetid: 0c85686a-53c1-4180-ba8c-2000e68a0d63
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5b69d2c043997e2947563de119bc4ee89fdf4e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679966"
---
# <a name="mssqlserver_511"></a><span data-ttu-id="c9d83-102">MSSQLSERVER_511</span><span class="sxs-lookup"><span data-stu-id="c9d83-102">MSSQLSERVER_511</span></span>
    
## <a name="details"></a><span data-ttu-id="c9d83-103">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c9d83-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9d83-104">Nome do Produto</span><span class="sxs-lookup"><span data-stu-id="c9d83-104">Product Name</span></span>|<span data-ttu-id="c9d83-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9d83-105">SQL Server</span></span>|  
|<span data-ttu-id="c9d83-106">ID do evento</span><span class="sxs-lookup"><span data-stu-id="c9d83-106">Event ID</span></span>|<span data-ttu-id="c9d83-107">511</span><span class="sxs-lookup"><span data-stu-id="c9d83-107">511</span></span>|  
|<span data-ttu-id="c9d83-108">Origem do Evento</span><span class="sxs-lookup"><span data-stu-id="c9d83-108">Event Source</span></span>|<span data-ttu-id="c9d83-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c9d83-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c9d83-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c9d83-110">Component</span></span>|<span data-ttu-id="c9d83-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c9d83-111">SQLEngine</span></span>|  
|<span data-ttu-id="c9d83-112">Nome simbólico</span><span class="sxs-lookup"><span data-stu-id="c9d83-112">Symbolic Name</span></span>|<span data-ttu-id="c9d83-113">ROW_TOOBIG</span><span class="sxs-lookup"><span data-stu-id="c9d83-113">ROW_TOOBIG</span></span>|  
|<span data-ttu-id="c9d83-114">Texto da mensagem</span><span class="sxs-lookup"><span data-stu-id="c9d83-114">Message Text</span></span>|<span data-ttu-id="c9d83-115">Não é possível criar uma linha com o tamanho %d que seja maior que o máximo permitido de %d.</span><span class="sxs-lookup"><span data-stu-id="c9d83-115">Cannot create a row of size %d which is greater than the allowable maximum of %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9d83-116">Explicação</span><span class="sxs-lookup"><span data-stu-id="c9d83-116">Explanation</span></span>  
 <span data-ttu-id="c9d83-117">A operação que você tentou excedeu o tamanho máximo de uma linha.</span><span class="sxs-lookup"><span data-stu-id="c9d83-117">The operation you have tried has exceeded the maximum size of a row.</span></span> <span data-ttu-id="c9d83-118">Normalmente, o tamanho máximo de uma linha é de 8.060 bytes.</span><span class="sxs-lookup"><span data-stu-id="c9d83-118">Usually, the maximum size of a row is 8,060 bytes.</span></span> <span data-ttu-id="c9d83-119">Alguns formatos de armazenamento contêm sobrecarga que pode reduzir o tamanho de linha disponível para dados.</span><span class="sxs-lookup"><span data-stu-id="c9d83-119">Some storage formats contain overhead that can reduce the row size that is available for data.</span></span> <span data-ttu-id="c9d83-120">Por exemplo, quando você usa colunas esparsas, o tamanho máximo de uma linha é de 8.018 bytes.</span><span class="sxs-lookup"><span data-stu-id="c9d83-120">For example, when you use sparse columns, the maximum size of a row is 8,018 bytes.</span></span> <span data-ttu-id="c9d83-121">Algumas operações que adicionam ou removem linhas e outras operações que alteram o tipo de dados de uma coluna exigem que a linha seja gravada novamente na página de dados e que a linha original seja posteriormente removida.</span><span class="sxs-lookup"><span data-stu-id="c9d83-121">Some operations that add or remove rows and some operations that change the data type of a column require the row to be rewritten on the data page, and then the original row is removed.</span></span> <span data-ttu-id="c9d83-122">Nessas operações, o limite efetivo do tamanho da linha é metade do limite máximo.</span><span class="sxs-lookup"><span data-stu-id="c9d83-122">In these operations, the effective limit to the size of the row is half the maximum limit.</span></span> <span data-ttu-id="c9d83-123">Isso ocorre porque a linha original e a linha modificada devem ser incluídas na página de dados por um período curto.</span><span class="sxs-lookup"><span data-stu-id="c9d83-123">This is because the original row and the modified row must both be contained on the data page for a short period.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="c9d83-124">Cada coluna **varchar (max)** ou **nvarchar (max)** não nula requer 24 bytes de alocação fixa adicional que conta em relação ao limite de 8.060 bytes de linha durante uma operação de classificação.</span><span class="sxs-lookup"><span data-stu-id="c9d83-124">Each non-null  **varchar(max)** or **nvarchar(max)** column requires 24 bytes of additional fixed allocation which counts against the 8,060 byte row limit during a sort operation.</span></span> <span data-ttu-id="c9d83-125">Isso pode criar um limite implícito para o número de colunas **varchar (max)** ou **nvarchar (max)** não nulas que podem ser criadas em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="c9d83-125">This can create an implicit limit to the number of non-null **varchar(max)** or **nvarchar(max)** columns that can be created in a table.</span></span> <span data-ttu-id="c9d83-126">Nenhum erro especial é fornecido quando a tabela é criada (além do aviso comum de que o tamanho máximo da linha excede o máximo permitido de 8060 bytes) ou no momento da inserção de dados.</span><span class="sxs-lookup"><span data-stu-id="c9d83-126">No special error is provided when the table is created (beyond the usual warning that the maximum row size exceeds the allowed maximum of 8060 bytes) or at the time of data insertion.</span></span> <span data-ttu-id="c9d83-127">Esse tamanho de linha pode causar erros (por exemplo, o erro 512) durante algumas operações normais, como uma atualização de chave de índice clusterizado ou classificações do conjunto de colunas completo, que os usuários não podem prever até que uma operação seja executada.</span><span class="sxs-lookup"><span data-stu-id="c9d83-127">This large row size can cause errors (such as error 512) during some normal operations, such as a clustered index key update, or sorts of the full column set, which users cannot anticipate until performing an operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9d83-128">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="c9d83-128">User Action</span></span>  
 <span data-ttu-id="c9d83-129">Se for possível, reduza o tamanho da linha.</span><span class="sxs-lookup"><span data-stu-id="c9d83-129">If it is possible, reduce the size of the row.</span></span>  
  
 <span data-ttu-id="c9d83-130">Se considerar que o problema está sendo causado por uma atualização no local da linha, será necessário alterar a tabela em várias etapas.</span><span class="sxs-lookup"><span data-stu-id="c9d83-130">If you think the problem is caused by an in-place update of the row, you must change the table in multiple steps.</span></span> <span data-ttu-id="c9d83-131">Crie uma tabela e transfira os dados para ela.</span><span class="sxs-lookup"><span data-stu-id="c9d83-131">Create a new table, and transfer the data into the new table.</span></span> <span data-ttu-id="c9d83-132">Depois, exclua a tabela original e renomeie a tabela nova ou, então, trunque a tabela original, modifique as linhas na tabela original e, depois, mova os dados de volta para ela.</span><span class="sxs-lookup"><span data-stu-id="c9d83-132">Then, either delete the original table and rename the new table, or truncate the original table, modify the rows in the original table, and then move the data back into it.</span></span>  
  
  
