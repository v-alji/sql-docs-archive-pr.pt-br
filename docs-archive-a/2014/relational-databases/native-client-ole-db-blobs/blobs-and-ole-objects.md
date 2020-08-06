---
title: BLOBs e objetos OLE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BLOBs, OLE objects
- BLOBs
- storage object [OLE DB]
- SQL Server Native Client OLE DB provider, BLOBs
- large data, OLE objects
ms.assetid: 767fa2f6-9cd2-436f-add5-e760bed29a58
author: rothja
ms.author: jroth
ms.openlocfilehash: 15f8b4915ba9b05a5be19854a2e27a2e8ff3a346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685608"
---
# <a name="blobs-and-ole-objects"></a><span data-ttu-id="38b78-102">BLOBs e objetos OLE</span><span class="sxs-lookup"><span data-stu-id="38b78-102">BLOBs and OLE Objects</span></span>
  <span data-ttu-id="38b78-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe a interface **ISequentialStream** para dar suporte ao acesso de consumidor aos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados **ntext**, **Text**, **Image**, **varchar (max)**, **nvarchar (max)**, **varbinary (max)** e XML como BLOBs (objetos binários grandes).</span><span class="sxs-lookup"><span data-stu-id="38b78-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ISequentialStream** interface to support consumer access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **ntext**, **text**, **image**, **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, and xml data types as binary large objects (BLOBs).</span></span> <span data-ttu-id="38b78-104">O método **Read** em **ISequentialStream** permite que o consumidor recupere muitos dados em partes gerenciáveis.</span><span class="sxs-lookup"><span data-stu-id="38b78-104">The **Read** method on **ISequentialStream** lets the consumer retrieve much data in manageable chunks.</span></span>  
  
 <span data-ttu-id="38b78-105">Para obter um exemplo que demonstra esse recurso, confira [Definir &#40;OLE DB&#41; de dados grandes](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="38b78-105">For a sample demonstrating this feature, see [Set Large Data &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span></span>  
  
 <span data-ttu-id="38b78-106">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo pode usar uma interface **IStorage** implementada pelo consumidor quando o consumidor fornece o ponteiro de interface em um acessador associado para modificação de dados.</span><span class="sxs-lookup"><span data-stu-id="38b78-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can use a consumer-implemented **IStorage** interface when the consumer provides the interface pointer in an accessor bound for data modification.</span></span>  
  
 <span data-ttu-id="38b78-107">Para tipos de dados de valor grande, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo verifica se há suposições de tamanho de tipo nas interfaces **IROWSET** e DDL.</span><span class="sxs-lookup"><span data-stu-id="38b78-107">For large value data types, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider checks for type size assumptions in **IRowset** and DDL interfaces.</span></span> <span data-ttu-id="38b78-108">Colunas com tipos de dados **varchar**, **nvarchar**e **varbinary** com tamanho máximo definido como ilimitado serão representadas como isduras por meio de conjuntos de linhas de esquema e interfaces que retornam tipos de dados de coluna.</span><span class="sxs-lookup"><span data-stu-id="38b78-108">Columns with **varchar**, **nvarchar**, and **varbinary** data types with max size set to unlimited will be represented as ISLONG through the schema rowsets and interfaces returning column data types.</span></span>  
  
 <span data-ttu-id="38b78-109">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe os tipos **varchar (max)**, **varbinary (max)** e **nvarchar (max)** como DBTYPE_STR, DBTYPE_BYTES e DBTYPE_WSTR, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="38b78-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **varchar(max)**, **varbinary(max)** and **nvarchar(max)** types as DBTYPE_STR, DBTYPE_BYTES and DBTYPE_WSTR respectively.</span></span>  
  
 <span data-ttu-id="38b78-110">Para trabalhar com esses tipos, um aplicativo tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="38b78-110">To work with these types an application has the following options:</span></span>  
  
-   <span data-ttu-id="38b78-111">Associar como o tipo (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span><span class="sxs-lookup"><span data-stu-id="38b78-111">Bind as the type (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span></span> <span data-ttu-id="38b78-112">Se o buffer não for suficientemente grande, ocorrerá truncamento, exatamente como para esses tipos em versões anteriores (embora agora haja valores maiores disponíveis).</span><span class="sxs-lookup"><span data-stu-id="38b78-112">If the buffer is not big enough truncation will occur, exactly as for these types in previous releases (although larger values are now available).</span></span>  
  
-   <span data-ttu-id="38b78-113">Associar como o tipo e também especificar DBTYPE_BYREF.</span><span class="sxs-lookup"><span data-stu-id="38b78-113">Bind as the type and also specify DBTYPE_BYREF.</span></span>  
  
-   <span data-ttu-id="38b78-114">Associar como DBTYPE_IUNKNOWN e usar streaming.</span><span class="sxs-lookup"><span data-stu-id="38b78-114">Bind as DBTYPE_IUNKNOWN and use streaming.</span></span>  
  
 <span data-ttu-id="38b78-115">Se associado a DBTYPE_IUNKNOWN, é usada a funcionalidade de fluxo ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="38b78-115">If bound to DBTYPE_IUNKNOWN, ISequentialStream stream functionality is used.</span></span> <span data-ttu-id="38b78-116">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte à associação de parâmetros de saída como DBTYPE_IUNKNOWN para tipos de dados de valor grande para facilitar cenários em que um procedimento armazenado retorna esses tipos de dados como valores de retorno que serão expostos como DBTYPE_IUNKNOWN ao cliente.</span><span class="sxs-lookup"><span data-stu-id="38b78-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports binding output parameters as DBTYPE_IUNKNOWN for large value data types to facilitate scenarios where a stored procedure returns these data types as return values which will be exposed as DBTYPE_IUNKNOWN to the client.</span></span>  
  
## <a name="storage-object-limitations"></a><span data-ttu-id="38b78-117">Limitações de objetos de armazenamento</span><span class="sxs-lookup"><span data-stu-id="38b78-117">Storage Object Limitations</span></span>  
  
-   <span data-ttu-id="38b78-118">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo pode dar suporte a apenas um único objeto de armazenamento aberto.</span><span class="sxs-lookup"><span data-stu-id="38b78-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can support only a single open storage object.</span></span> <span data-ttu-id="38b78-119">As tentativas de abrir mais de um objeto de armazenamento (para obter uma referência em mais de um ponteiro da interface **ISequentialStream**) retornam DBSTATUS_E_CANTCREATE.</span><span class="sxs-lookup"><span data-stu-id="38b78-119">Attempts to open more than one storage object (to get a reference on more than one **ISequentialStream** interface pointer) return DBSTATUS_E_CANTCREATE.</span></span>  
  
-   <span data-ttu-id="38b78-120">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, o valor padrão da propriedade DBPROP_BLOCKINGSTORAGEOBJECTS somente leitura é VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="38b78-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the default value of the DBPROP_BLOCKINGSTORAGEOBJECTS read-only property is VARIANT_TRUE.</span></span> <span data-ttu-id="38b78-121">Isso indica que se um objeto de armazenamento está ativo, alguns métodos (diferentes daqueles nos objetos de armazenamento) falharão com E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="38b78-121">This indicates that if a storage object is active, some methods (other than those on the storage objects) will fail with E_UNEXPECTED.</span></span>  
  
-   <span data-ttu-id="38b78-122">O comprimento dos dados apresentados por um objeto de armazenamento implementado pelo consumidor deve ser conhecido pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo quando o acessador de linha que faz referência ao objeto de armazenamento é criado.</span><span class="sxs-lookup"><span data-stu-id="38b78-122">The length of data presented by a consumer-implemented storage object must be made known to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider when the row accessor that references the storage object is created.</span></span> <span data-ttu-id="38b78-123">O consumidor deve associar um indicador de comprimento na estrutura DBBINDING usada para a criação do acessador.</span><span class="sxs-lookup"><span data-stu-id="38b78-123">The consumer must bind a length indicator in the DBBINDING structure used for accessor creation.</span></span>  
  
-   <span data-ttu-id="38b78-124">Se uma linha contiver mais de um único valor de dados grandes e DBPROP_ACCESSORDER não for DBPROPVAL_AO_RANDOM, o consumidor deverá usar um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjunto de linhas com suporte do cursor do provedor de OLE DB de cliente nativo para recuperar dados de linha ou processar todos os valores de dados grandes antes de recuperar outros valores de linha.</span><span class="sxs-lookup"><span data-stu-id="38b78-124">If a row contains more than a single large data value and DBPROP_ACCESSORDER is not DBPROPVAL_AO_RANDOM, the consumer must either use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider cursor-supported rowset to retrieve row data or process all large data values before retrieving other row values.</span></span> <span data-ttu-id="38b78-125">Se DBPROP_ACCESSORDER for DBPROPVAL_AO_RANDOM, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo armazenará em cache todos os tipos de dados XML como BLOBs (objetos binários grandes) para que possam ser acessados em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="38b78-125">If DBPROP_ACCESSORDER is DBPROPVAL_AO_RANDOM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider caches all the xml data types as binary large objects (BLOBs) so that it can be accessed in any order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38b78-126">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="38b78-126">In This Section</span></span>  
  
-   [<span data-ttu-id="38b78-127">Obtendo dados grandes</span><span class="sxs-lookup"><span data-stu-id="38b78-127">Getting Large Data</span></span>](getting-large-data.md)  
  
-   [<span data-ttu-id="38b78-128">Definindo dados grandes</span><span class="sxs-lookup"><span data-stu-id="38b78-128">Setting Large Data</span></span>](setting-large-data.md)  
  
-   [<span data-ttu-id="38b78-129">Suporte de transmissão a parâmetros de saída BLOB</span><span class="sxs-lookup"><span data-stu-id="38b78-129">Streaming Support for BLOB Output Parameters</span></span>](streaming-support-for-blob-output-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="38b78-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38b78-130">See Also</span></span>  
 <span data-ttu-id="38b78-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="38b78-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="38b78-132">Usando tipos de valor grande</span><span class="sxs-lookup"><span data-stu-id="38b78-132">Using Large Value Types</span></span>](../native-client/features/using-large-value-types.md)  
  
  
