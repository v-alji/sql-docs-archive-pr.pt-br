---
title: IRowsetFastLoad::Commit (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::Commit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Commit method
ms.assetid: 19de9128-b91a-4626-847f-af721edaa24e
author: rothja
ms.author: jroth
ms.openlocfilehash: cfdf355919f65fd2cedacd09249e2aae59321390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582434"
---
# <a name="irowsetfastloadcommit-ole-db"></a><span data-ttu-id="89288-102">IRowsetFastLoad::Commit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="89288-102">IRowsetFastLoad::Commit (OLE DB)</span></span>
  <span data-ttu-id="89288-103">Marca o término de um lote de linhas inseridas e escreve as linhas na tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="89288-103">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="89288-104">Para obter exemplos, confira [Copiar Dados em massa usando IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) e [Enviar dados de blob para o SQL Server usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="89288-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89288-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="89288-105">Syntax</span></span>  
  
```  
  
HRESULT Commit(  
BOOL   
fDone  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="89288-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="89288-106">Arguments</span></span>  
 <span data-ttu-id="89288-107">*fDone*[in]</span><span class="sxs-lookup"><span data-stu-id="89288-107">*fDone*[in]</span></span>  
 <span data-ttu-id="89288-108">Se FALSE, o conjunto de linhas manterá validade e poderá ser usado pelo consumidor para inserção de linha adicional.</span><span class="sxs-lookup"><span data-stu-id="89288-108">If FALSE, the rowset maintains validity and can be used by the consumer for additional row insertion.</span></span> <span data-ttu-id="89288-109">Caso seja TRUE, o conjunto de linhas perde validade e nenhuma inserção adicional pode ser feita pelo consumidor.</span><span class="sxs-lookup"><span data-stu-id="89288-109">If TRUE, the rowset loses validity and no further insertion can be done by the consumer.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="89288-110">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="89288-110">Return Code Values</span></span>  
 <span data-ttu-id="89288-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="89288-111">S_OK</span></span>  
 <span data-ttu-id="89288-112">O método teve êxito e todos os dados inseridos foram escritos na tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89288-112">The method succeeded and all inserted data has been written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="89288-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89288-113">E_FAIL</span></span>  
 <span data-ttu-id="89288-114">Ocorreu um erro específico de provedor.</span><span class="sxs-lookup"><span data-stu-id="89288-114">A provider-specific error occurred.</span></span> <span data-ttu-id="89288-115">Recupere informações de erro para o texto de erro específico do provedor.</span><span class="sxs-lookup"><span data-stu-id="89288-115">Retrieve error information for the specific error text from the provider.</span></span>  
  
 <span data-ttu-id="89288-116">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="89288-116">E_UNEXPECTED</span></span>  
 <span data-ttu-id="89288-117">O método foi chamado em um conjunto de linhas de cópia em massa invalidado anteriormente pelo método **IRowsetFastLoad::Commit**.</span><span class="sxs-lookup"><span data-stu-id="89288-117">The method was called on a bulk copy rowset previously invalidated by the **IRowsetFastLoad::Commit** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89288-118">Comentários</span><span class="sxs-lookup"><span data-stu-id="89288-118">Remarks</span></span>  
 <span data-ttu-id="89288-119">Um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjunto de linhas de cópia em massa do provedor de OLE DB de cliente nativo se comporta como um conjunto de linhas de modo de atualização atrasada.</span><span class="sxs-lookup"><span data-stu-id="89288-119">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowset behaves as a delayed-update mode rowset.</span></span> <span data-ttu-id="89288-120">Conforme o usuário insere dados de linha pelo conjunto de linhas, as linhas inseridas são tratadas da mesma forma que as inserções pendentes em um conjunto de linhas que dá suporte a **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="89288-120">As the user inserts row data through the rowset, inserted rows are treated in the same fashion as pending inserts on a rowset supporting **IRowsetUpdate**.</span></span>  
  
 <span data-ttu-id="89288-121">O consumidor deve chamar o método **Commit** no conjunto de linhas de cópia em massa para gravar as linhas inseridas na tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da mesma forma que o método **IRowsetUpdate::Update** é usado para enviar linhas pendentes para uma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89288-121">The consumer must call the **Commit** method on the bulk copy rowset to write inserted rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table in the same way as the **IRowsetUpdate::Update** method is used to submit pending rows to an instance of SQL Server.</span></span>  
  
 <span data-ttu-id="89288-122">Caso o consumidor libere a referência no conjunto de linhas de cópia em massa sem chamar o método **Commit**, todas as linhas inseridas não gravadas previamente serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="89288-122">If the consumer releases its reference on the bulk copy rowset without calling the **Commit** method, all inserted rows not previously written are lost.</span></span>  
  
 <span data-ttu-id="89288-123">O consumidor pode processar em lotes as linhas inseridas chamando o método **Commit** com o argumento *fDone* definido como FALSE.</span><span class="sxs-lookup"><span data-stu-id="89288-123">The consumer can batch inserted rows by calling the **Commit** method with the *fDone* argument set to FALSE.</span></span> <span data-ttu-id="89288-124">Quando *fDone* é definido como TRUE, o conjunto de linhas se torna inválido.</span><span class="sxs-lookup"><span data-stu-id="89288-124">When *fDone*is set to TRUE, the rowset becomes invalid.</span></span> <span data-ttu-id="89288-125">Um conjunto de linhas de cópia em massa inválido dá suporte apenas à interface **ISupportErrorInfo** e ao método **IRowsetFastLoad::Release**.</span><span class="sxs-lookup"><span data-stu-id="89288-125">An invalid bulk copy rowset supports only the **ISupportErrorInfo** interface and **IRowsetFastLoad::Release** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89288-126">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="89288-126">See Also</span></span>  
 [<span data-ttu-id="89288-127">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="89288-127">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
