---
title: Níveis de isolamento (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, transactions
- isolation levels [OLE DB]
- transactions [OLE DB]
- SQL Server Native Client OLE DB provider, transactions
ms.assetid: d70ee72c-6e2a-4bcd-9456-4a697a866361
author: rothja
ms.author: jroth
ms.openlocfilehash: c7f6cbff4e68eaedd3e78a82cddd872ba5f8f19e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575083"
---
# <a name="isolation-levels-ole-db"></a><span data-ttu-id="0934e-102">Níveis de isolamento (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="0934e-102">Isolation Levels (OLE DB)</span></span>
  <span data-ttu-id="0934e-103">Clientes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem controlar os níveis de isolamento de transação para uma conexão.</span><span class="sxs-lookup"><span data-stu-id="0934e-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients can control transaction-isolation levels for a connection.</span></span> <span data-ttu-id="0934e-104">Para controlar o nível de isolamento de transação, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor de OLE DB de cliente nativo usa:</span><span class="sxs-lookup"><span data-stu-id="0934e-104">To control transaction-isolation level, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer uses:</span></span>  
  
-   <span data-ttu-id="0934e-105">DBPROPSET_SESSION propriedade DBPROP_SESS_AUTOCOMMITISOLEVELS para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] modo de confirmação automática padrão do provedor de OLE DB do cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="0934e-105">DBPROPSET_SESSION property DBPROP_SESS_AUTOCOMMITISOLEVELS for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default autocommit mode.</span></span>  
  
     <span data-ttu-id="0934e-106">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] padrão do provedor de OLE DB de cliente nativo para o nível é DBPROPVAL_TI_READCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="0934e-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider default for the level is DBPROPVAL_TI_READCOMMITTED.</span></span>  
  
-   <span data-ttu-id="0934e-107">O parâmetro *isoLevel* do método **ITransactionLocal::StartTransaction** para transações de confirmação manual locais.</span><span class="sxs-lookup"><span data-stu-id="0934e-107">The *isoLevel* parameter of the **ITransactionLocal::StartTransaction** method for local manual-commit transactions.</span></span>  
  
-   <span data-ttu-id="0934e-108">O parâmetro *isoLevel* do método **ITransactionDispenser::BeginTransaction** para transações distribuídas coordenadas do MS DTC.</span><span class="sxs-lookup"><span data-stu-id="0934e-108">The *isoLevel* parameter of the **ITransactionDispenser::BeginTransaction** method for MS DTC-coordinated distributed transactions.</span></span>  
  
 <span data-ttu-id="0934e-109">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite acesso de somente leitura ao nível de isolamento de leitura suja.</span><span class="sxs-lookup"><span data-stu-id="0934e-109">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows read-only access at the dirty read isolation level.</span></span> <span data-ttu-id="0934e-110">Todos os outros níveis restringem a simultaneidade aplicando bloqueios a objetos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0934e-110">All other levels restrict concurrency by applying locks to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span> <span data-ttu-id="0934e-111">À medida que o cliente exigir níveis de simultaneidade maiores, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aplica restrições maiores ao acesso simultâneo aos dados.</span><span class="sxs-lookup"><span data-stu-id="0934e-111">As the client requires greater concurrency levels, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applies greater restrictions on concurrent access to data.</span></span> <span data-ttu-id="0934e-112">Para manter o nível mais alto de acesso simultâneo aos dados, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor do provedor de OLE DB de cliente nativo deve controlar de forma inteligente suas solicitações para níveis de simultaneidade específicos.</span><span class="sxs-lookup"><span data-stu-id="0934e-112">To maintain the highest level of concurrent access to data, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer should intelligently control its requests for specific concurrency levels.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0934e-113">O [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] introduziu o nível de isolamento do instantâneo.</span><span class="sxs-lookup"><span data-stu-id="0934e-113">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] introduced snapshot isolation level.</span></span> <span data-ttu-id="0934e-114">Para obter mais informações, confira [Trabalhando com o isolamento de instantâneos](../native-client/features/working-with-snapshot-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="0934e-114">For more information, see [Working with Snapshot Isolation](../native-client/features/working-with-snapshot-isolation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0934e-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0934e-115">See Also</span></span>  
 [<span data-ttu-id="0934e-116">Transações</span><span class="sxs-lookup"><span data-stu-id="0934e-116">Transactions</span></span>](transactions.md)  
  
  
