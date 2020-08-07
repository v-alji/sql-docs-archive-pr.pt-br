---
title: IRowsetFastLoad (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IRowsetFastLoad interface
ms.assetid: d19a7097-48d9-409a-aff9-277891b7aca7
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ecf72f0015d9ed197b3b7a33d4f9bb3246134b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582429"
---
# <a name="irowsetfastload-ole-db"></a><span data-ttu-id="6589f-102">IRowsetFastLoad (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="6589f-102">IRowsetFastLoad (OLE DB)</span></span>
  <span data-ttu-id="6589f-103">A `IRowsetFastLoad` interface expõe o suporte para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] operações de cópia em massa baseadas em memória.</span><span class="sxs-lookup"><span data-stu-id="6589f-103">The `IRowsetFastLoad` interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory-based bulk-copy operations.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="6589f-104">Os consumidores do provedor de OLE DB de cliente nativo usam a interface para adicionar dados rapidamente a uma [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabela existente.</span><span class="sxs-lookup"><span data-stu-id="6589f-104">Native Client OLE DB provider consumers use the interface to rapidly add data to an existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="6589f-105">Se você definir SSPROP_ENABLEFASTLOAD como VARIANT_TRUE para uma sessão, não poderá ler dados de conjuntos de linhas subsequentemente passados como retorno dessa sessão.</span><span class="sxs-lookup"><span data-stu-id="6589f-105">If you set SSPROP_ENABLEFASTLOAD to VARIANT_TRUE for a session, you cannot read data from rowsets subsequently returned from that session.</span></span> <span data-ttu-id="6589f-106">Quando SSPROP_ENABLEFASTLOAD for definido como VARIANT_TRUE, todos os conjuntos de linhas criados na sessão serão do tipo IRowsetFastLoad.</span><span class="sxs-lookup"><span data-stu-id="6589f-106">When SSPROP_ENABLEFASTLOAD is set to VARIANT_TRUE, all rowsets created on the session will be of type IRowsetFastLoad.</span></span> <span data-ttu-id="6589f-107">Os conjuntos de linhas IRowsetFastLoad não dão suporte à funcionalidade de fetch de conjuntos de linhas; portanto, os dados desses conjuntos de linhas não podem ser lidos.</span><span class="sxs-lookup"><span data-stu-id="6589f-107">IRowsetFastLoad rowsets do not support rowset fetch functionality; therefore, data from these rowsets cannot be read.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6589f-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6589f-108">In This Section</span></span>  
  
|<span data-ttu-id="6589f-109">Método</span><span class="sxs-lookup"><span data-stu-id="6589f-109">Method</span></span>|<span data-ttu-id="6589f-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="6589f-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6589f-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6589f-111">IRowsetFastLoad::Commit &#40;OLE DB&#41;</span></span>](irowsetfastload-commit-ole-db.md)|<span data-ttu-id="6589f-112">Marca o término de um lote de linhas inseridas e escreve as linhas na tabela [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6589f-112">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="6589f-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6589f-113">IRowsetFastLoad::InsertRow &#40;OLE DB&#41;</span></span>](irowsetfastload-insertrow-ole-db.md)|<span data-ttu-id="6589f-114">Adiciona uma linha ao conjunto de linhas de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="6589f-114">Adds a row to the bulk copy rowset.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6589f-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6589f-115">See Also</span></span>  
 <span data-ttu-id="6589f-116">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="6589f-116">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="6589f-117">[Copiar Dados em massa usando o IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="6589f-117">[Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) </span></span>  
 [<span data-ttu-id="6589f-118">Enviar dados BLOB ao SQL SERVER usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6589f-118">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
  
