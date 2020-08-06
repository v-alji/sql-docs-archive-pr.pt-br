---
title: Procedimentos armazenados do sistema XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- system stored procedures [SQL Server], XML
- sp_xml_removedocument
- OPENXML statement, system stored procedures
- sp_xml_preparedocument
- XML [SQL Server], system stored procedures
ms.assetid: e60c7f85-6823-4d28-93d6-b053d08cc830
author: rothja
ms.author: jroth
ms.openlocfilehash: 2008294fe5bc532dfb6883656420b4189e4da7b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575675"
---
# <a name="xml-system-stored-procedures"></a><span data-ttu-id="a311d-102">Procedimentos armazenados do sistema XML</span><span class="sxs-lookup"><span data-stu-id="a311d-102">XML System Stored Procedures</span></span>
  <span data-ttu-id="a311d-103">O SQL Server fornece os seguintes procedimentos armazenados do sistema que são usados junto com o OPENXML:</span><span class="sxs-lookup"><span data-stu-id="a311d-103">SQL Server provides the following system stored procedures that are used together with OPENXML:</span></span>  
  
-   [<span data-ttu-id="a311d-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a311d-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql)  
  
-   [<span data-ttu-id="a311d-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a311d-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql)  
  
 <span data-ttu-id="a311d-106">Para escrever consultas usando OPENXML, é necessário primeiro criar uma representação interna do documento XML chamando **sp_xml_preparedocument**.</span><span class="sxs-lookup"><span data-stu-id="a311d-106">To write queries by using OPENXML, you must first create an internal representation of the XML document by calling **sp_xml_preparedocument**.</span></span> <span data-ttu-id="a311d-107">O procedimento armazenado retorna um identificador para a representação interna do documento XML.</span><span class="sxs-lookup"><span data-stu-id="a311d-107">The stored procedure returns a handle to the internal representation of the XML document.</span></span> <span data-ttu-id="a311d-108">Em seguida, esse identificador é passado para o OPENXML.</span><span class="sxs-lookup"><span data-stu-id="a311d-108">This handle is then passed to OPENXML.</span></span> <span data-ttu-id="a311d-109">O OPENXML fornece exibições de conjuntos de linhas do documento baseado em XPaths.</span><span class="sxs-lookup"><span data-stu-id="a311d-109">OPENXML provides rowset views of the document based on XPaths.</span></span> <span data-ttu-id="a311d-110">Especificamente, isso é um padrão de linha e um ou mais padrões de coluna.</span><span class="sxs-lookup"><span data-stu-id="a311d-110">Specifically, this is one row pattern and one or more column patterns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a311d-111">O identificador do documento retornado por **sp_xml_preparedocument** é válido durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="a311d-111">The document handle that is returned by **sp_xml_preparedocument** is valid for the duration of the session.</span></span>  
  
 <span data-ttu-id="a311d-112">A representação interna de um documento XML pode ser removida da memória chamando o procedimento armazenado do sistema **sp_xml_removedocument** .</span><span class="sxs-lookup"><span data-stu-id="a311d-112">The internal representation of an XML document can be removed from memory by calling the **sp_xml_removedocument** system stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a311d-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a311d-113">See Also</span></span>  
 <span data-ttu-id="a311d-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a311d-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="a311d-115">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a311d-115">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
