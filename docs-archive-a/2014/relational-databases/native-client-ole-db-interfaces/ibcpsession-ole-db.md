---
title: IBCPSession (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IBCPSession interface
ms.assetid: 00d0311f-8b71-4ad6-824d-0e89119347a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d32da9c06a200d5924dbae18d6b7513f46c88ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684690"
---
# <a name="ibcpsession-ole-db"></a><span data-ttu-id="1746c-102">IBCPSession (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="1746c-102">IBCPSession (OLE DB)</span></span>
  <span data-ttu-id="1746c-103">A interface **IBCPSession** expõe o suporte a operações de cópia em massa baseada em arquivo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1746c-103">The **IBCPSession** interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file-based bulk copy operations.</span></span> <span data-ttu-id="1746c-104">A interface **IBCPSession** é exposta no provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client no mesmo nível que Sessões.</span><span class="sxs-lookup"><span data-stu-id="1746c-104">The **IBCPSession** interface is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider under the same level as Sessions.</span></span> <span data-ttu-id="1746c-105">No provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, os objetos de fonte de dados são fábricas de objetos de sessão e as operações de cópia em massa são especificadas na propriedade de conexão SSPROP_ENABLEBULKCOPY.</span><span class="sxs-lookup"><span data-stu-id="1746c-105">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, data source objects are factories for Session objects, and bulk copy operations are specified in the connection property SSPROP_ENABLEBULKCOPY.</span></span> <span data-ttu-id="1746c-106">Além disso, a propriedade SSPROP_ENABLEFASTLOAD deve ser definida como verdadeira.</span><span class="sxs-lookup"><span data-stu-id="1746c-106">In addition, the SSPROP_ENABLEFASTLOAD property should be set to true.</span></span>  
  
 <span data-ttu-id="1746c-107">Chamar o método **IDBCreateSession::CreateSession** resultará na criação de um objeto **BulkCopySession** .</span><span class="sxs-lookup"><span data-stu-id="1746c-107">Calling the **IDBCreateSession::CreateSession** method will then result in the creation of a **BulkCopySession** object.</span></span> <span data-ttu-id="1746c-108">Todos os métodos de cópia em massa com base em arquivo expostos pelo objeto **IBCPSession** poderão, então, ser chamados com assinaturas semelhantes na interface **IBCPSession** desse objeto **IBCPSession** .</span><span class="sxs-lookup"><span data-stu-id="1746c-108">All the file-based bulk copy methods exposed through the **IBCPSession** object are then callable with nearly similar signatures on this **IBCPSession** object's **IBCPSession** interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1746c-109">O provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client oferece suporte a operações de cópia em massa com base em memória por meio da interface [IRowsetFastLoad](irowsetfastload-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="1746c-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports memory-based bulk copy operations through the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="1746c-110">Para obter mais informações sobre como usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo para operações de cópia em massa, consulte [executando operações de cópia em massa](../native-client/features/performing-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="1746c-110">For more information about using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider for bulk copy operations, see [Performing Bulk Copy Operations](../native-client/features/performing-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="1746c-111">Para obter um exemplo de como usar a interface **IBCPSession**, confira [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="1746c-111">For a sample showing how to use the **IBCPSession** interface, see [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1746c-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1746c-112">In This Section</span></span>  
  
|<span data-ttu-id="1746c-113">Método</span><span class="sxs-lookup"><span data-stu-id="1746c-113">Method</span></span>|<span data-ttu-id="1746c-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="1746c-114">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1746c-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolfmt-ole-db.md)|<span data-ttu-id="1746c-116">Cria uma associação entre variáveis de programa e colunas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1746c-116">Creates a binding between program variables and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns.</span></span>|  
|[<span data-ttu-id="1746c-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolumns-ole-db.md)|<span data-ttu-id="1746c-118">Define o número de campos que devem ser associados às colunas de uma tabela do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1746c-118">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="1746c-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcontrol-ole-db.md)|<span data-ttu-id="1746c-120">Define as opções para uma operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="1746c-120">Sets the options for a bulk copy operation.</span></span>|  
|[<span data-ttu-id="1746c-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span></span>](ibcpsession-bcpdone-ole-db.md)|<span data-ttu-id="1746c-122">Confirma as linhas restantes a serem enviadas ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1746c-122">Commits the remaining rows to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="1746c-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span></span>](ibcpsession-bcpexec-ole-db.md)|<span data-ttu-id="1746c-124">Executa a operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="1746c-124">Performs the bulk copy operation.</span></span>|  
|[<span data-ttu-id="1746c-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span></span>](ibcpsession-bcpinit-ole-db.md)|<span data-ttu-id="1746c-126">Inicializa a estrutura de cópia em massa, executa alguma verificação de erros, verifica se os nomes dos arquivos de formato e de dados estão corretos e, então, os abre.</span><span class="sxs-lookup"><span data-stu-id="1746c-126">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>|  
|[<span data-ttu-id="1746c-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpreadfmt-ole-db.md)|<span data-ttu-id="1746c-128">Lê informações de formato relativas a cada coluna no arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="1746c-128">Reads format information for each column from the format file.</span></span>|  
|[<span data-ttu-id="1746c-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpwritefmt-ole-db.md)|<span data-ttu-id="1746c-130">Grava informações de formato relativas a cada coluna no arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="1746c-130">Writes format information for each column to the format file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1746c-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1746c-131">See Also</span></span>  
 [<span data-ttu-id="1746c-132">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1746c-132">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
