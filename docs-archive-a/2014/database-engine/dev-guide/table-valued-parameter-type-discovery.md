---
title: Descoberta de tipo de parâmetro com valor de tabela | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, type discovery
ms.assetid: f55818c2-ebb5-4cf6-8c0c-0da41f592560
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab8d837e4ddf74256e4bae70f772557ec8ff67f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681123"
---
# <a name="table-valued-parameter-type-discovery"></a><span data-ttu-id="b5e2a-102">Descoberta do tipo de parâmetro com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="b5e2a-102">Table-Valued Parameter Type Discovery</span></span>
  <span data-ttu-id="b5e2a-103">O consumidor, ou seja, o aplicativo cliente que usa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo – pode descobrir o tipo de cada parâmetro de comando se o texto do comando tiver sido fornecido ao provedor de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-103">The consumer-that is, the client application using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider-can discover the type of each command parameter if the command text has been given to the OLE DB Provider.</span></span> <span data-ttu-id="b5e2a-104">Depois que o tipo de um parâmetro com valor de tabela for conhecido, o consumidor pode descobrir as informações de metadados de cada coluna específica do parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-104">After the type of a table-valued parameter is known, the consumer can discover the metadata information for each individual column of the table-valued parameter.</span></span>  
  
 <span data-ttu-id="b5e2a-105">As informações de tipo dos parâmetros de procedimento são compatíveis com ICommandWithParameters::GetParameterInfo para a maioria dos tipos de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-105">The type information of procedure parameters is supported by ICommandWithParameters::GetParameterInfo for most parameter types.</span></span> <span data-ttu-id="b5e2a-106">Começando com [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o, com a introdução de tipos definidos pelo usuário e o `xml` tipo de dados, o método GetParameterInfo não era suficiente para essa finalidade porque não era possível fornecer informações de tipo definido pelo usuário (nome, esquema e catálogo) por meio de ICommandWithParameters.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], with the introduction of user-defined types and the `xml` data type, the GetParameterInfo method was not sufficient for this purpose because it was not possible to provide user-defined type information (name, schema, and catalog) through ICommandWithParameters.</span></span> <span data-ttu-id="b5e2a-107">Uma interface nova, a ISSCommandWithParameters, foi definida para fornecer informações de tipo estendidas.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-107">A new interface, ISSCommandWithParameters, was defined to provide extended type information.</span></span>  
  
 <span data-ttu-id="b5e2a-108">Para parâmetros com valor de tabela, você também usa a interface ISSCommandWithParameters para descobrir informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-108">For table-valued parameters, you also use the ISSCommandWithParameters interface to discover detailed information.</span></span> <span data-ttu-id="b5e2a-109">O cliente chama ISSCommandWithParameters::GetParameterInfo após preparar o objeto de comando.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-109">The client calls ISSCommandWithParameters::GetParameterInfo after preparing the command object.</span></span> <span data-ttu-id="b5e2a-110">Para parâmetros com valor de tabela, o membro *wType* da estrutura DBPARAMINFO é definido como DBTYPE_TABLE pelo provedor.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-110">For table-valued parameters, the *wType* member of the DBPARAMINFO structure is set to DBTYPE_TABLE by the provider.</span></span> <span data-ttu-id="b5e2a-111">O campo *ulParamSize* da estrutura DBPARAMINFO tem um valor de ~0.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-111">The *ulParamSize* field of DBPARAMINFO structure has a value of ~0.</span></span>  
  
 <span data-ttu-id="b5e2a-112">O cliente solicitará as propriedades adicionais (nome de catálogo do tipo de parâmetro com valor de tabela, nome de esquema do tipo de parâmetro com valor de tabela, nome do tipo de parâmetro com valor de tabela, ordenação de colunas e colunas padrão) usando o ISSCommandWithParameters::GetParameterProperties.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-112">The consumer would then request additional properties (table-valued parameter type catalog name, table-valued parameter type schema name, table-valued parameter type name, column ordering, and default columns) by using ISSCommandWithParameters::GetParameterProperties.</span></span>  
  
 <span data-ttu-id="b5e2a-113">Depois que o nome do tipo é conhecido, para recuperar as informações de coluna específicas, o consumidor deve chamar IOpenRowset::OpenRowsetor ou obter o conjunto de linhas DBSCHEMA_TABLE_TYPE_COLUMNS especificando o nome do tipo de parâmetro com valor de tabela como nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="b5e2a-113">After the type name is known, to retrieve the individual column information the consumer must either call IOpenRowset::OpenRowsetor obtain the DBSCHEMA_TABLE_TYPE_COLUMNS rowset by specifying the table-valued parameter type name as the table name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e2a-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b5e2a-114">See Also</span></span>  
 <span data-ttu-id="b5e2a-115">[Os parâmetros com valor de tabela &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="b5e2a-115">[Table-Valued Parameters &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="b5e2a-116">Usar parâmetros com valor de tabela &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b5e2a-116">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
