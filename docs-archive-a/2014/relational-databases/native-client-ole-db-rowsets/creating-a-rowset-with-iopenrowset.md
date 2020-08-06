---
title: Criando um conjunto de linhas com IOpenRowset | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- IOpenRowset interface
- rowsets [OLE DB], creating
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, creating
ms.assetid: e8bc3de7-4b97-4de9-8df8-e11947d24045
author: rothja
ms.author: jroth
ms.openlocfilehash: bf74466a698d39f74b9531adaa54c79c75e50ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684691"
---
# <a name="creating-a-rowset-with-iopenrowset"></a><span data-ttu-id="05f0d-102">Criando um conjunto de linhas com IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="05f0d-102">Creating a Rowset with IOpenRowset</span></span>
  <span data-ttu-id="05f0d-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte ao método **IOpenRowset:: OPENROWSET** com as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="05f0d-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the **IOpenRowset::OpenRowset** method with the following restrictions:</span></span>  
  
-   <span data-ttu-id="05f0d-104">É necessário especificar uma exibição ou uma tabela base em uma estrutura DBID (ID de banco de dados) para a qual o parâmetro *pTableID* aponte.</span><span class="sxs-lookup"><span data-stu-id="05f0d-104">A base table or view must be specified in a database ID (DBID) structure that the *pTableID* parameter points to.</span></span>  
  
-   <span data-ttu-id="05f0d-105">O membro *eKind* de DBID precisa indicar DBKIND_NAME.</span><span class="sxs-lookup"><span data-stu-id="05f0d-105">The DBID *eKind* member must indicate DBKIND_NAME.</span></span>  
  
-   <span data-ttu-id="05f0d-106">O membro *uName* de DBID precisa especificar o nome de uma exibição ou uma tabela base existente como uma cadeia de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="05f0d-106">The DBID *uName* member must specify the name of an existing base table or a view as a Unicode character string.</span></span>  
  
-   <span data-ttu-id="05f0d-107">O parâmetro *pIndexID* de **OpenRowset** precisa ser NULL.</span><span class="sxs-lookup"><span data-stu-id="05f0d-107">The *pIndexID* parameter of **OpenRowset** must be NULL.</span></span>  
  
 <span data-ttu-id="05f0d-108">O conjunto de resultados de **IOpenRowset::OpenRowset** contém um único conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="05f0d-108">The result set of **IOpenRowset::OpenRowset** contains a single rowset.</span></span> <span data-ttu-id="05f0d-109">Os conjuntos de resultados que contêm um único conjunto de linhas podem ter suporte de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursores.</span><span class="sxs-lookup"><span data-stu-id="05f0d-109">Result sets that contain a single rowset can be supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors.</span></span> <span data-ttu-id="05f0d-110">O suporte de cursor permite ao desenvolvedor usar mecanismos de simultaneidade do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05f0d-110">Cursor support allows the developer to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05f0d-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="05f0d-111">See Also</span></span>  
 [<span data-ttu-id="05f0d-112">Conjuntos de linhas</span><span class="sxs-lookup"><span data-stu-id="05f0d-112">Rowsets</span></span>](rowsets.md)  
  
  
