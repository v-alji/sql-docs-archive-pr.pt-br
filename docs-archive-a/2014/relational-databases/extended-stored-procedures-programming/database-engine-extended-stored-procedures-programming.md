---
title: Programando procedimentos armazenados estendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- gateway applications [SQL Server]
- extended stored procedures [SQL Server], about extended stored procedures
- Open Data Services [SQL Server]
- ODS [SQL Server]
ms.assetid: 561305cd-c803-48af-9eec-2c19f4d311ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 30792cc2b431e35a8f7df5ff7bbb2c228892d5c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576400"
---
# <a name="programming-extended-stored-procedures"></a><span data-ttu-id="6e5b0-102">Programando procedimentos armazenados estendidos</span><span class="sxs-lookup"><span data-stu-id="6e5b0-102">Programming Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6e5b0-103">Em vez disso, use a Integração CLR.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="6e5b0-104">No passado, o Open Data Services era usado para gravar aplicativos de servidor, como gateways para ambientes de banco de dados que não fossem o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-104">In the past, Open Data Services was used to write server applications, such as gateways to non-SQL Server database environments.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="6e5b0-105">o não [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a partes obsoletas da API Open Data Services.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support the obsolete portions of the Open Data Services API.</span></span> <span data-ttu-id="6e5b0-106">A única parte da API Open Data Services original ainda suportada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é a das funções de procedimento armazenado estendido, de modo que a API foi renomeada para a API de procedimento armazenado estendido.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-106">The only part of the original Open Data Services API still supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are the extended stored procedure functions, so the API has been renamed to the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="6e5b0-107">Com o surgimento de tecnologias mais novas e mais avançadas, como as consultas distribuídas e a integração CLR, a necessidade por aplicativos de API de procedimento armazenado estendido foi amplamente substituída.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-107">With the emergence of newer and more powerful technologies, such as distributed queries and CLR Integration, the need for Extended Stored Procedure API applications has largely been replaced.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e5b0-108">Se você tiver aplicativos de gateway existentes, não poderá usar opends60.dll que acompanha o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para executar os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-108">If you have existing gateway applications, you cannot use the opends60.dll that ships with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run the applications.</span></span> <span data-ttu-id="6e5b0-109">Os aplicativos de gateway já não são mais suportados.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-109">Gateway applications are no longer supported.</span></span>  
  
## <a name="extended-stored-procedures-vs-clr-integration"></a><span data-ttu-id="6e5b0-110">Procedimentos armazenados estendidos e Integração de CLR</span><span class="sxs-lookup"><span data-stu-id="6e5b0-110">Extended Stored Procedures vs. CLR Integration</span></span>  
 <span data-ttu-id="6e5b0-111">Nas versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], os procedimentos armazenados estendidos forneciam o único mecanismo disponível para os desenvolvedores de aplicativos de banco de dados gravarem lógica no lado do servidor, o que era difícil de expressar ou impossível de gravar no [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e5b0-111">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], extended stored procedures (XPs) provided the only mechanism that was available for database application developers to write server-side logic that was either hard to express or impossible to write in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6e5b0-112">A Integração CLR fornece uma alternativa mais robusta para gravar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-112">CLR Integration provides a more robust alternative to writing such stored procedures.</span></span> <span data-ttu-id="6e5b0-113">Além disso, com a Integração CLR, a lógica que costumava ser gravada na forma de procedimentos armazenados é, em geral, melhor expressada como funções com valor de tabela, o que permite que os resultados criados pela função sejam consultados nas instruções SELECT, inserindo-os na cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="6e5b0-113">Furthermore, with CLR Integration, logic that used to be written in the form of stored procedures is often better expressed as table-valued functions, which allow the results constructed by the function to be queried in SELECT statements by embedding them in the FROM clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e5b0-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e5b0-114">See Also</span></span>  
 <span data-ttu-id="6e5b0-115">[Visão geral da integração do CLR&#41; &#40;Common Language Runtime](../clr-integration/common-language-runtime-integration-overview.md) </span><span class="sxs-lookup"><span data-stu-id="6e5b0-115">[Common Language Runtime &#40;CLR&#41; Integration Overview](../clr-integration/common-language-runtime-integration-overview.md) </span></span>  
 [<span data-ttu-id="6e5b0-116">Funções com valor de tabela CLR</span><span class="sxs-lookup"><span data-stu-id="6e5b0-116">CLR Table-Valued Functions</span></span>](../clr-integration-database-objects-user-defined-functions/clr-table-valued-functions.md)  
  
  
