---
title: Coleções de esquemas XML grandes e condições de memória insuficiente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- out-of-memory conditions
- XML schema collections [SQL Server], large
ms.assetid: 29b9d839-aaaf-48fb-be17-840c751f36f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443207bbbdff5db7e54d61fcebabe70e34cc540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686170"
---
# <a name="large-xml-schema-collections-and-out-of-memory-conditions"></a><span data-ttu-id="d4b54-102">Coleções de esquema XML grandes e condições de memória insuficiente</span><span class="sxs-lookup"><span data-stu-id="d4b54-102">Large XML Schema Collections and Out-of-Memory Conditions</span></span>
  <span data-ttu-id="d4b54-103">Durante uma chamada à função XML_SCHEMA_NAMESPACE() interna em uma coleção de esquema XML grande ou ao tentar descartar grandes coleções de esquema XML, pode ocorrer uma condição de memória insuficiente.</span><span class="sxs-lookup"><span data-stu-id="d4b54-103">During a call to the built-in XML_SCHEMA_NAMESPACE() function on a large XML schema collection, or when you try to drop large XML schema collections, an out-of-memory condition may occur.</span></span> <span data-ttu-id="d4b54-104">Os seguintes soluções podem ser usadas para tratar essa situação:</span><span class="sxs-lookup"><span data-stu-id="d4b54-104">The following are solutions you can use to handle this:</span></span>  
  
-   <span data-ttu-id="d4b54-105">Quando a carga do sistema estiver leve, use o comando DROP_XML_SCHEMA_COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="d4b54-105">When the system load is light, use the DROP_XML_SCHEMA_COLLECTION command.</span></span> <span data-ttu-id="d4b54-106">Se isso falhar, coloque o banco de dados em modo do usuário único usando a instrução ALTER DATABASE e tente DROP XML SCHEMA COLLECTION novamente.</span><span class="sxs-lookup"><span data-stu-id="d4b54-106">If this fails, put the database in single-user mode by using the ALTER DATABASE statement and trying DROP XML SCHEMA COLLECTION again.</span></span> <span data-ttu-id="d4b54-107">Se a coleção de esquema XML existir em **master**, **model**ou **tempdb**uma reinicialização do servidor será necessária para o modo de usuário único.</span><span class="sxs-lookup"><span data-stu-id="d4b54-107">If the XML schema collection exists in **master**, **model**, or **tempdb**, a server restart is required for single-user mode.</span></span>  
  
-   <span data-ttu-id="d4b54-108">Ao chamar XML_SCHEMA_NAMESPACE, você pode tentar recuperar um único namespace do esquema XML. A chamada pode ser tentada quando a carga do sistema estiver mais leve ou em modo de usuário único.</span><span class="sxs-lookup"><span data-stu-id="d4b54-108">When you call the XML_SCHEMA_NAMESPACE, you can try to retrieve a single XML schema namespace, you can try the call when the system load is lighter, or you can try the call in single-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b54-109">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4b54-109">See Also</span></span>  
 [<span data-ttu-id="d4b54-110">Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor</span><span class="sxs-lookup"><span data-stu-id="d4b54-110">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
