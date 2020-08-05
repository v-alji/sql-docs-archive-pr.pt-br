---
title: Quando usar SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- SQLNCLI, about SQL Server Native Client
- data access [SQL Server Native Client], about SQL Server Native Client
ms.assetid: 08f18b36-209d-4cf7-9623-ebc61859a91d
author: rothja
ms.author: jroth
ms.openlocfilehash: f8aeb34525bbe5c1b003e8fd95e7a414025965a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572512"
---
# <a name="when-to-use-sql-server-native-client"></a><span data-ttu-id="1e20f-102">Quando usar o SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="1e20f-102">When to Use SQL Server Native Client</span></span>
  <span data-ttu-id="1e20f-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client é uma tecnologia que você pode usar para acessar dados em um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e20f-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is one technology that you can use to access data in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  <span data-ttu-id="1e20f-104">Para obter uma discussão sobre as diferentes tecnologias de acesso a dados, confira [Roteiro das tecnologias de acesso a dados](https://go.microsoft.com/fwlink/?LinkID=179186)</span><span class="sxs-lookup"><span data-stu-id="1e20f-104">For a discussion of the different data-access technologies, see [Data Access Technologies Road Map](https://go.microsoft.com/fwlink/?LinkID=179186)</span></span>  
  
 <span data-ttu-id="1e20f-105">Ao decidir se deve usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client como a tecnologia de acesso a dados do seu aplicativo, você deve considerar vários fatores.</span><span class="sxs-lookup"><span data-stu-id="1e20f-105">When deciding whether to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client as the data access technology of your application, you should consider several factors.</span></span>  
  
 <span data-ttu-id="1e20f-106">No caso de novos aplicativos, se você estiver usando uma linguagem de programação gerenciada, como o Microsoft Visual C# ou o Visual Basic, e precisar acessar os novos recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use o provedor de dados .NET Framework para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], que faz parte do .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1e20f-106">For new applications, if you're using a managed programming language such as Microsoft Visual C# or Visual Basic, and you need to access the new features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should use the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which is part of the .NET Framework.</span></span>  
  
 <span data-ttu-id="1e20f-107">Caso esteja desenvolvendo um aplicativo baseado no COM e precise acessar os novos recursos incorporados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="1e20f-107">If you are developing a COM-based application and need to access the new features introduced in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="1e20f-108">Caso não precise do acesso aos novos recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você poderá continuar a usar o WDAC (Windows Data Access Components).</span><span class="sxs-lookup"><span data-stu-id="1e20f-108">If you don't need access to the new features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can continue to use Windows Data Access Components (WDAC).</span></span>  
  
 <span data-ttu-id="1e20f-109">Para aplicativos OLE DB e ODBC existentes, o principal problema é se você precisa acessar os novos recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e20f-109">For existing OLE DB and ODBC applications, the primary issue is whether you need to access the new features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1e20f-110">Caso tenha um aplicativo consolidado que não precise dos novos recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você poderá continuar usando o WDAC.</span><span class="sxs-lookup"><span data-stu-id="1e20f-110">If you have a mature application that does not need the new features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can continue to use WDAC.</span></span> <span data-ttu-id="1e20f-111">Mas se você precisar acessar esses novos recursos, como o [tipo de dados XML](/sql/t-sql/xml/xml-transact-sql), deverá usar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="1e20f-111">But if you do need to access those new features, such as the [xml data type](/sql/t-sql/xml/xml-transact-sql), you should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="1e20f-112">Tanto o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client quanto o MDAC oferecem suporte ao isolamento de transação de leitura confirmada usando controle de versão de linha, mas apenas o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client oferece suporte ao isolamento da transação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="1e20f-112">Both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and MDAC support read committed transaction isolation using row versioning, but only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client supports snapshot transaction isolation.</span></span> <span data-ttu-id="1e20f-113">(Em termos de programação, o isolamento de transação de leitura confirmada por meio do controle de versão de linha é igual à transação de leitura confirmada.)</span><span class="sxs-lookup"><span data-stu-id="1e20f-113">(In programming terms, read committed transaction isolation with row versioning is the same as Read-Committed transaction.)</span></span>  
  
 <span data-ttu-id="1e20f-114">Para obter informações sobre as diferenças entre o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client e o MDAC, consulte [atualizando um aplicativo para SQL Server Native Client do MDAC](../../relational-databases/native-client/applications/updating-an-application-to-sql-server-native-client-from-mdac.md).</span><span class="sxs-lookup"><span data-stu-id="1e20f-114">For information about the differences between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and MDAC, see [Updating an Application to SQL Server Native Client from MDAC](../../relational-databases/native-client/applications/updating-an-application-to-sql-server-native-client-from-mdac.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e20f-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1e20f-115">See Also</span></span>  
 <span data-ttu-id="1e20f-116">[Programação de SQL Server Native Client](../../relational-databases/native-client/sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="1e20f-116">[SQL Server Native Client Programming](../../relational-databases/native-client/sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="1e20f-117">[Tópicos de instruções sobre ODBC](../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="1e20f-117">[ODBC How-to Topics](../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 [<span data-ttu-id="1e20f-118">Tópicos de instruções do OLE DB</span><span class="sxs-lookup"><span data-stu-id="1e20f-118">OLE DB How-to Topics</span></span>](../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
