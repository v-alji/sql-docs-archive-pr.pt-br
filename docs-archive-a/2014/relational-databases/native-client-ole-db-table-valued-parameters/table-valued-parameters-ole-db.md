---
title: Parâmetros com valor de tabela (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, table-valued parameters
- table-valued parameters (OLE DB)
ms.assetid: 4298b73d-615b-4d28-9843-03b4d5fc489e
author: rothja
ms.author: jroth
ms.openlocfilehash: 41d125bcb254125d7f7562ca1873e8af03dab929
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684171"
---
# <a name="table-valued-parameters-ole-db"></a><span data-ttu-id="2cb21-102">Parâmetros com valor de tabela (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="2cb21-102">Table-Valued Parameters (OLE DB)</span></span>
  <span data-ttu-id="2cb21-103">Esta seção descreve o suporte a parâmetros com valor de tabela no provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="2cb21-103">This section describes support for table-valued parameters in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider.</span></span> <span data-ttu-id="2cb21-104">Para obter informações gerais adicionais, consulte [parâmetros com valor de tabela &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="2cb21-104">For additional overview information, see [Table-Valued Parameters &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span></span> <span data-ttu-id="2cb21-105">Para ver uma amostra, confira [Usar parâmetros com valor de tabela &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="2cb21-105">For a sample, see [Use Table-Valued Parameters &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cb21-106">Comentários</span><span class="sxs-lookup"><span data-stu-id="2cb21-106">Remarks</span></span>  
 <span data-ttu-id="2cb21-107">Atualmente, você pode enviar dados de várias linhas ao servidor como parâmetros para um procedimento com conjuntos de parâmetros (o parâmetro DBPARAMS em `ICommand::Execute`).</span><span class="sxs-lookup"><span data-stu-id="2cb21-107">Currently, you can send multirow data to the server as parameters to a procedure with parameter sets (the DBPARAMS parameter in `ICommand::Execute`).</span></span> <span data-ttu-id="2cb21-108">Com conjuntos de parâmetros, todo elemento do conjunto tem que ser enviado ao servidor em uma solicitação RPC (chamada de procedimento remoto) separada.</span><span class="sxs-lookup"><span data-stu-id="2cb21-108">With parameter sets, every element of the set has to be sent in a separate remote procedure call (RPC) request to the server.</span></span> <span data-ttu-id="2cb21-109">Os parâmetros com valor de tabela fornecem uma funcionalidade semelhante, mas interagem melhor com o servidor.</span><span class="sxs-lookup"><span data-stu-id="2cb21-109">Table-valued parameters provide similar functionality, but there is better integration with the server.</span></span> <span data-ttu-id="2cb21-110">Isso reduz o número de solicitações RPC e habilita operações baseadas em conjunto no servidor.</span><span class="sxs-lookup"><span data-stu-id="2cb21-110">This reduces the number of RPC requests and enables set-based operations on the server.</span></span>  
  
 <span data-ttu-id="2cb21-111">Os parâmetros com valor de tabela são suportados no provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client como objetos OLE DB `Rowset`.</span><span class="sxs-lookup"><span data-stu-id="2cb21-111">Table-value parameters are supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider as OLE DB `Rowset` objects.</span></span> <span data-ttu-id="2cb21-112">Qualquer objeto `Rowset` poderia ser fornecido pelo consumidor (ou seja, o aplicativo cliente usando o provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) como um espaço reservado para parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="2cb21-112">Any `Rowset` object could be provided by the consumer (that is, the client application using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider) as a placeholder for table-valued parameter parameters.</span></span> <span data-ttu-id="2cb21-113">Os parâmetros com valor de tabela são tratados como os outros tipos de parâmetro do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cb21-113">Table-valued parameters are treated like other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parameter types.</span></span> <span data-ttu-id="2cb21-114">O provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fornece interfaces de criação, descoberta, especificação, associação e de esquema.</span><span class="sxs-lookup"><span data-stu-id="2cb21-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider provides creation, discovery, specification, binding and schema interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cb21-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2cb21-115">In This Section</span></span>  
  
-   [<span data-ttu-id="2cb21-116">Criação do conjunto de linhas do parâmetro com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="2cb21-116">Table-Valued Parameter Rowset Creation</span></span>](table-valued-parameter-rowset-creation.md)  
  
-   [<span data-ttu-id="2cb21-117">Descoberta do tipo de parâmetro com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="2cb21-117">Table-Valued Parameter Type Discovery</span></span>](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md)  
  
-   [<span data-ttu-id="2cb21-118">Executando comandos que contêm parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="2cb21-118">Executing Commands Containing Table-Valued Parameters</span></span>](executing-commands-containing-table-valued-parameters.md)  
  
-   [<span data-ttu-id="2cb21-119">Inserindo dados em parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="2cb21-119">Inserting Data into Table-Valued Parameters</span></span>](inserting-data-into-table-valued-parameters.md)  
  
-   [<span data-ttu-id="2cb21-120">Conjuntos de linhas de esquema alterados para parâmetros com valor de tabela de OLE DB</span><span class="sxs-lookup"><span data-stu-id="2cb21-120">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>](schema-rowsets-changed-for-ole-db-table-valued-parameters.md)  
  
-   [<span data-ttu-id="2cb21-121">Suporte ao tipo de parâmetro com valor de tabela OLE DB</span><span class="sxs-lookup"><span data-stu-id="2cb21-121">OLE DB Table-Valued Parameter Type Support</span></span>](ole-db-table-valued-parameter-type-support.md)  
  
-   [<span data-ttu-id="2cb21-122">Suporte ao tipo de parâmetro com valor de tabela OLE DB &#40;Métodos&#41;</span><span class="sxs-lookup"><span data-stu-id="2cb21-122">OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;</span></span>](ole-db-table-valued-parameter-type-support-methods.md)  
  
-   [<span data-ttu-id="2cb21-123">Suporte ao tipo de parâmetro com valor de tabela do OLE DB &#40;Propriedades&#41;</span><span class="sxs-lookup"><span data-stu-id="2cb21-123">OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;</span></span>](ole-db-table-valued-parameter-type-support-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="2cb21-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2cb21-124">See Also</span></span>  
 <span data-ttu-id="2cb21-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="2cb21-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="2cb21-126">Usar parâmetros com valor de tabela &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2cb21-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
