---
title: Suporte ao tipo de parâmetro com valor de tabela do OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (OLE DB)
ms.assetid: 147036a0-260e-4f81-8b3b-89209e023a32
author: rothja
ms.author: jroth
ms.openlocfilehash: 48d5fd780b2eaa2fc18e39071d3b10fde897b82c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572027"
---
# <a name="ole-db-table-valued-parameter-type-support"></a><span data-ttu-id="659b9-102">Suporte ao tipo de parâmetro com valor de tabela OLE DB</span><span class="sxs-lookup"><span data-stu-id="659b9-102">OLE DB Table-Valued Parameter Type Support</span></span>
  <span data-ttu-id="659b9-103">Este tópico descreve suporte ao tipo OLE DB para parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="659b9-103">This topic describes OLE DB type support for table-value parameters.</span></span>  
  
## <a name="table-valued-parameter-rowset-object"></a><span data-ttu-id="659b9-104">Objeto de conjunto de linhas de parâmetro com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="659b9-104">Table-Valued Parameter Rowset Object</span></span>  
 <span data-ttu-id="659b9-105">É possível criar um objeto de conjunto de linhas especializado para parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="659b9-105">You can create a specialized rowset object for table-valued parameters.</span></span> <span data-ttu-id="659b9-106">Você cria o objeto de conjunto de linhas de parâmetro com valor de tabela usando ITableDefinitionWithConstraints::CreateTableWithConstraints ou IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="659b9-106">You create the table-valued parameter rowset object by using ITableDefinitionWithConstraints::CreateTableWithConstraints or IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="659b9-107">Para fazer isso, defina o membro *eKind* do parâmetro *pTableID* como DBKIND_GUID_NAME e forneça o CLSID_ROWSET_INMEMORY como o membro *guid*.</span><span class="sxs-lookup"><span data-stu-id="659b9-107">To do this, set the *eKind* member of the *pTableID* parameter to DBKIND_GUID_NAME, and provide the CLSID_ROWSET_INMEMORY as the *guid* member.</span></span> <span data-ttu-id="659b9-108">O nome do tipo de servidor para parâmetro com valor de tabela deve ser especificado no membro *pwszName* de *pTableID* ao usar IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="659b9-108">The server type name for the table-valued parameter must be specified in the *pwszName* member of *pTableID* when using IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="659b9-109">O objeto de conjunto de linhas para parâmetros com valor de tabela se comporta como um objeto do provedor OLE DB do SQL Server Native Client normal.</span><span class="sxs-lookup"><span data-stu-id="659b9-109">The table-valued parameter rowset object behaves like a regular SQL Server Native Client OLE DB Provider object.</span></span>  
  
```  
const GUID CLSID_ROWSET_TVP =   
{0xc7ef28d5, 0x7bee, 0x443f, {0x86, 0xda, 0xe3, 0x98, 0x4f, 0xcd, 0x4d, 0xf9}};  
  
CoType RowsetTVP  
{  
[mandatory] interface IAccessor;  
[mandatory] interface IColumnsInfo;  
[mandatory] interface IConvertType;  
[mandatory] interface IRowset;  
[mandatory] interface IRowsetInfo;  
[optional]  interface IColumnsRowset;  
[optional]  interface IRowsetChange;  
[optional]  interface ISupportErrorInfo;  
};  
```  
  
## <a name="dbtype_table"></a><span data-ttu-id="659b9-110">DBTYPE_TABLE</span><span class="sxs-lookup"><span data-stu-id="659b9-110">DBTYPE_TABLE</span></span>  
 <span data-ttu-id="659b9-111">Um tipo novo, DBTYPE_TABLE, representa um tipo de tabela.</span><span class="sxs-lookup"><span data-stu-id="659b9-111">A new type, DBTYPE_TABLE, represents a table type.</span></span> <span data-ttu-id="659b9-112">Esse tipo especifica parâmetros com valor de tabela em várias interfaces OLE DB em que um DBTYPE é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="659b9-112">This type specifies table-valued parameters in various OLE DB interfaces where a DBTYPE is required.</span></span>  
  
```  
#define DBTYPE_TABLE (143)  
```  
  
 <span data-ttu-id="659b9-113">DBTYPE_TABLE tem o mesmo formato de DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="659b9-113">DBTYPE_TABLE has the same format as DBTYPE_IUNKNOWN.</span></span> <span data-ttu-id="659b9-114">Trata-se de um ponteiro para um objeto no buffer de dados.</span><span class="sxs-lookup"><span data-stu-id="659b9-114">It is a pointer to an object in the data buffer.</span></span> <span data-ttu-id="659b9-115">Para obter a especificação completa nas associações, o consumidor preenche o buffer DBOBJECT, com *iid* definido como uma das interfaces de objeto de conjunto de linhas (IID_IRowset).</span><span class="sxs-lookup"><span data-stu-id="659b9-115">For complete specification in the bindings, the consumer fills up the DBOBJECT buffer, with *iid* set to one of the rowset object interfaces (IID_IRowset).</span></span> <span data-ttu-id="659b9-116">Se nenhum DBOBJECT for especificado nas associações, IID_IRowset será assumido.</span><span class="sxs-lookup"><span data-stu-id="659b9-116">If no DBOBJECT is specified in the bindings, IID_IRowset will be assumed.</span></span>  
  
 <span data-ttu-id="659b9-117">Não há suporte para conversões para e de DBTYPE_TABLE para qualquer outro tipo.</span><span class="sxs-lookup"><span data-stu-id="659b9-117">Conversions to and from DBTYPE_TABLE for any other types are not supported.</span></span> <span data-ttu-id="659b9-118">IConvertType::CanConvert retornará S_FALSE em uma conversão não compatível para qualquer solicitação que não seja a conversão de DBTYPE_TABLE em DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="659b9-118">IConvertType::CanConvert will return S_FALSE for unsupported conversion for any request other than DBTYPE_TABLE to DBTYPE_TABLE conversion.</span></span> <span data-ttu-id="659b9-119">Isso supõe DBCONVERTFLAGS_PARAMETER no objeto Command.</span><span class="sxs-lookup"><span data-stu-id="659b9-119">This assumes DBCONVERTFLAGS_PARAMETER on the Command object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="659b9-120">Métodos</span><span class="sxs-lookup"><span data-stu-id="659b9-120">Methods</span></span>  
 <span data-ttu-id="659b9-121">Para obter informações sobre métodos do OLE DB que dão suporte a parâmetros com valor de tabela, confira [Suporte ao tipo de parâmetro com valor de tabela OLE DB &#40;Métodos&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span><span class="sxs-lookup"><span data-stu-id="659b9-121">For information about OLE DB methods that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="659b9-122">Propriedades</span><span class="sxs-lookup"><span data-stu-id="659b9-122">Properties</span></span>  
 <span data-ttu-id="659b9-123">Para obter informações sobre propriedades do OLE DB que dão suporte a parâmetros com valor de tabela, confira [Suporte ao tipo de parâmetro com valor de tabela OLE DB &#40;Propriedades&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span><span class="sxs-lookup"><span data-stu-id="659b9-123">For information about OLE DB properties that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659b9-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="659b9-124">See Also</span></span>  
 <span data-ttu-id="659b9-125">[Os parâmetros com valor de tabela &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="659b9-125">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="659b9-126">Usar parâmetros com valor de tabela &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="659b9-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
