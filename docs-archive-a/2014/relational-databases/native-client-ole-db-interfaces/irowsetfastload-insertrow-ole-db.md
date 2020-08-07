---
title: IRowsetFastLoad::InsertRow (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::InsertRow (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- InsertRow method
ms.assetid: 594d3461-34d2-41e7-8ad4-bd2753601ab6
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e9ea952f27574270ee333919f778814ff3de462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582430"
---
# <a name="irowsetfastloadinsertrow-ole-db"></a><span data-ttu-id="c36c7-102">IRowsetFastLoad::InsertRow (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="c36c7-102">IRowsetFastLoad::InsertRow (OLE DB)</span></span>
  <span data-ttu-id="c36c7-103">Adiciona uma linha ao conjunto de linhas de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="c36c7-103">Adds a row to the bulk copy rowset.</span></span> <span data-ttu-id="c36c7-104">Para obter exemplos, confira [Copiar Dados em massa usando IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) e [Enviar dados de blob para o SQL Server usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="c36c7-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36c7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c36c7-105">Syntax</span></span>  
  
```  
  
HRESULT InsertRow(  
HACCESSOR  
hAccessor  
,  
void*  
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c36c7-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c36c7-106">Arguments</span></span>  
 <span data-ttu-id="c36c7-107">*hAccessor*[in]</span><span class="sxs-lookup"><span data-stu-id="c36c7-107">*hAccessor*[in]</span></span>  
 <span data-ttu-id="c36c7-108">O identificador do acessador que define os dados de linha para cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="c36c7-108">The handle of the accessor defining the row data for bulk copy.</span></span> <span data-ttu-id="c36c7-109">O acessador referenciado é um acessador de linha, que associa a memória de propriedade do consumidor contendo valores de dados.</span><span class="sxs-lookup"><span data-stu-id="c36c7-109">The accessor referenced is a row accessor, binding consumer-owned memory containing data values.</span></span>  
  
 <span data-ttu-id="c36c7-110">*pData*[in]</span><span class="sxs-lookup"><span data-stu-id="c36c7-110">*pData*[in]</span></span>  
 <span data-ttu-id="c36c7-111">Um ponteiro para a memória de propriedade do consumidor que contém valores de dados.</span><span class="sxs-lookup"><span data-stu-id="c36c7-111">A pointer to the consumer-owned memory containing data values.</span></span> <span data-ttu-id="c36c7-112">Para obter mais informações, consulte [Estruturas DBBINDING](https://go.microsoft.com/fwlink/?LinkId=65955).</span><span class="sxs-lookup"><span data-stu-id="c36c7-112">For more information, see [DBBINDING Structures](https://go.microsoft.com/fwlink/?LinkId=65955).</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="c36c7-113">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="c36c7-113">Return Code Values</span></span>  
 <span data-ttu-id="c36c7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c36c7-114">S_OK</span></span>  
 <span data-ttu-id="c36c7-115">O método foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="c36c7-115">The method succeeded.</span></span> <span data-ttu-id="c36c7-116">Todos os valores de status associados para todas as colunas têm o valor DBSTATUS_S_OK ou DBSTATUS_S_NULL.</span><span class="sxs-lookup"><span data-stu-id="c36c7-116">Any bound status values for all columns have value DBSTATUS_S_OK or DBSTATUS_S_NULL.</span></span>  
  
 <span data-ttu-id="c36c7-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c36c7-117">E_FAIL</span></span>  
 <span data-ttu-id="c36c7-118">Ocorreu um erro.</span><span class="sxs-lookup"><span data-stu-id="c36c7-118">An error occurred.</span></span> <span data-ttu-id="c36c7-119">As informações do erro estão disponíveis nas interfaces de erro do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="c36c7-119">Error information is available from the rowset's error interfaces.</span></span>  
  
 <span data-ttu-id="c36c7-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c36c7-120">E_INVALIDARG</span></span>  
 <span data-ttu-id="c36c7-121">O argumento *pData* foi definido como um ponteiro NULL.</span><span class="sxs-lookup"><span data-stu-id="c36c7-121">The *pData* argument was set to a NULL pointer.</span></span>  
  
 <span data-ttu-id="c36c7-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c36c7-122">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c36c7-123">SQLNCLI11 não pôde alocar memória suficiente para concluir a solicitação.</span><span class="sxs-lookup"><span data-stu-id="c36c7-123">SQLNCLI11 was unable to allocate sufficient memory to complete the request.</span></span>  
  
 <span data-ttu-id="c36c7-124">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="c36c7-124">E_UNEXPECTED</span></span>  
 <span data-ttu-id="c36c7-125">O método foi chamado em um conjunto de linhas de cópia em massa invalidado anteriormente pelo método [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="c36c7-125">The method was called on a bulk copy rowset previously invalidated by the [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="c36c7-126">DB_E_BADACCESSORHANDLE</span><span class="sxs-lookup"><span data-stu-id="c36c7-126">DB_E_BADACCESSORHANDLE</span></span>  
 <span data-ttu-id="c36c7-127">O argumento *hAccessor* fornecido pelo consumidor era inválido.</span><span class="sxs-lookup"><span data-stu-id="c36c7-127">The *hAccessor* argument provided by the consumer was invalid.</span></span>  
  
 <span data-ttu-id="c36c7-128">DB_E_BADACCESSORTYPE</span><span class="sxs-lookup"><span data-stu-id="c36c7-128">DB_E_BADACCESSORTYPE</span></span>  
 <span data-ttu-id="c36c7-129">O acessador especificado não era um acessador de linha ou não especificou a memória de propriedade do consumidor.</span><span class="sxs-lookup"><span data-stu-id="c36c7-129">The specified accessor was not a row accessor or did not specify consumer-owned memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c36c7-130">Comentários</span><span class="sxs-lookup"><span data-stu-id="c36c7-130">Remarks</span></span>  
 <span data-ttu-id="c36c7-131">Um erro ao converter dados do consumidor no tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para uma coluna gera um retorno E_FAIL do provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c36c7-131">An error converting consumer data to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for a column causes an E_FAIL return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="c36c7-132">Os dados podem ser transmitidos para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em qualquer método **InsertRow** ou apenas no método **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c36c7-132">Data can be transmitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on any **InsertRow** method or only on **Commit** method.</span></span> <span data-ttu-id="c36c7-133">O aplicativo do consumidor pode chamar o método **InsertRow** muitas vezes com dados incorretos antes ser avisado de que há um erro de conversão de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="c36c7-133">The consumer application can call the **InsertRow** method many times with erroneous data before it receives notice that a data type conversion error exists.</span></span> <span data-ttu-id="c36c7-134">Como o método **Commit** assegura que todos os dados sejam especificados corretamente pelo consumidor, ele pode usar o método **Commit** apropriadamente para validar os dados, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c36c7-134">Because the **Commit** method ensures that all data is correctly specified by the consumer, the consumer can use the **Commit** method appropriately to validate data as necessary.</span></span>  
  
 <span data-ttu-id="c36c7-135">Os conjuntos de linhas de cópia em massa do provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client são somente gravação.</span><span class="sxs-lookup"><span data-stu-id="c36c7-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowsets are write-only.</span></span> <span data-ttu-id="c36c7-136">O provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client não expõe nenhum método que permite consultas do consumidor do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="c36c7-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes no methods allowing consumer query of the rowset.</span></span> <span data-ttu-id="c36c7-137">Para encerrar o processamento, o consumidor pode liberar sua referência na interface [IRowsetFastLoad](irowsetfastload-ole-db.md) sem chamar o método **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c36c7-137">To terminate processing, the consumer can release its reference on the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface without calling the **Commit** method.</span></span> <span data-ttu-id="c36c7-138">Não há nenhum recurso para acessar uma linha inserida pelo consumidor no conjunto de linhas e alterar seus valores ou para removê-la individualmente do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="c36c7-138">There are no facilities for accessing a consumer-inserted row in the rowset and changing its values, or removing it individually from the rowset.</span></span>  
  
 <span data-ttu-id="c36c7-139">As linhas copiadas em massa são formatadas no servidor para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c36c7-139">Bulk copied rows are formatted on the server for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c36c7-140">O formato de linha é afetado por todas as opções que possam ter sido definidas para a conexão ou sessão, como ANSI_PADDING.</span><span class="sxs-lookup"><span data-stu-id="c36c7-140">The row format is affected by any options that may have been set for the connection or session such as ANSI_PADDING.</span></span> <span data-ttu-id="c36c7-141">Essa opção é ativada por padrão para qualquer conexão feita por meio do provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c36c7-141">This option is set on by default for any connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36c7-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c36c7-142">See Also</span></span>  
 [<span data-ttu-id="c36c7-143">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c36c7-143">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
