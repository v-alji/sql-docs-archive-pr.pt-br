---
title: Criando um aplicativo de provedor de OLE DB de SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, application creation
- applications [SQL Server Native Client]
- OLE DB, creating applications
ms.assetid: f3ae6815-f32d-4913-a1a2-2ba2f20cfd88
author: rothja
ms.author: jroth
ms.openlocfilehash: a661f23cdacc4b581dadbe7625cb6e2ea318857f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679927"
---
# <a name="creating-a-sql-server-native-client-ole-db-provider-application"></a><span data-ttu-id="c46a6-102">Criando um aplicativo provedor OLE DB do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c46a6-102">Creating a SQL Server Native Client OLE DB Provider Application</span></span>
  <span data-ttu-id="c46a6-103">A criação de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aplicativo de provedor de OLE DB de cliente nativo envolve estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c46a6-103">Creating a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider application involves these steps:</span></span>  
  
1.  <span data-ttu-id="c46a6-104">Estabelecimento de uma conexão a uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c46a6-104">Establishing a connection to a data source.</span></span>  
  
2.  <span data-ttu-id="c46a6-105">Execução de um comando.</span><span class="sxs-lookup"><span data-stu-id="c46a6-105">Executing a command.</span></span>  
  
3.  <span data-ttu-id="c46a6-106">Processamento dos resultados.</span><span class="sxs-lookup"><span data-stu-id="c46a6-106">Processing the results.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c46a6-107">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="c46a6-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="c46a6-108">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="c46a6-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="c46a6-109">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="c46a6-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="c46a6-110">Se for necessário persistir as credenciais, criptografe-as com a [Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span><span class="sxs-lookup"><span data-stu-id="c46a6-110">If you must persist credentials, you should encrypt them with [the Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c46a6-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c46a6-111">In This Section</span></span>  
  
-   [<span data-ttu-id="c46a6-112">Estabelecendo uma conexão com uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c46a6-112">Establishing a Connection to a Data Source</span></span>](establishing-a-connection-to-a-data-source.md)  
  
-   [<span data-ttu-id="c46a6-113">Executando um comando</span><span class="sxs-lookup"><span data-stu-id="c46a6-113">Executing a Command</span></span>](executing-a-command.md)  
  
-   [<span data-ttu-id="c46a6-114">Processando resultados</span><span class="sxs-lookup"><span data-stu-id="c46a6-114">Processing Results</span></span>](processing-results.md)  
  
-   [<span data-ttu-id="c46a6-115">Sobre propriedades OLE DB</span><span class="sxs-lookup"><span data-stu-id="c46a6-115">About OLE DB Properties</span></span>](about-ole-db-properties.md)  
  
-   [<span data-ttu-id="c46a6-116">Usando a cláusula OUTPUT com OLE DB no SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c46a6-116">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>](using-the-output-clause-with-ole-db-in-sql-server-native-client.md)  
  
## <a name="see-also"></a><span data-ttu-id="c46a6-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c46a6-117">See Also</span></span>  
 [<span data-ttu-id="c46a6-118">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c46a6-118">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
