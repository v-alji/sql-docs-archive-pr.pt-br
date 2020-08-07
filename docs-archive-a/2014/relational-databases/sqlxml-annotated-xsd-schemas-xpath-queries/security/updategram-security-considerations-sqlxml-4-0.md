---
title: Considerações de segurança do updategram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- security [SQLXML], updategrams
- updategrams [SQLXML], security
ms.assetid: 00dc6cf4-a2e8-4cca-bdd6-d5122102a82d
author: rothja
ms.author: jroth
ms.openlocfilehash: eb0319285e6e8cf6e8b3e70f3eb6b9923de06f55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581720"
---
# <a name="updategram-security-considerations-sqlxml-40"></a><span data-ttu-id="94072-102">Considerações sobre segurança para diagramas de atualização (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="94072-102">Updategram Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="94072-103">A seguir são apresentadas diretrizes de segurança para o uso de diagramas de atualização:</span><span class="sxs-lookup"><span data-stu-id="94072-103">The following are security guidelines for using updategrams:</span></span>  
  
-   <span data-ttu-id="94072-104">Evite usar mapeamento padrão quando usar diagramas de atualização para atualizar dados.</span><span class="sxs-lookup"><span data-stu-id="94072-104">Avoid using default mapping when you use updategrams to update data.</span></span> <span data-ttu-id="94072-105">Quando você usar mapeamento padrão, um nome de elemento em um diagrama de atualização será mapeado para um nome de tabela e um nome de atributo será mapeado para uma coluna.</span><span class="sxs-lookup"><span data-stu-id="94072-105">When you use default mapping, an element name in an updategram maps to a table name, and an attribute name maps to a column.</span></span> <span data-ttu-id="94072-106">Isso expõe as informações de coluna e de tabela de banco de dados no banco de dados, o que pode representar um risco de segurança potencial.</span><span class="sxs-lookup"><span data-stu-id="94072-106">This exposes the database table and column information in the database, which can be a potential security risk.</span></span> <span data-ttu-id="94072-107">Se, em vez disso, você especificar um esquema de mapeamento separado que mapeie os elementos e os atributos em um diagrama de atualização para colunas e tabelas do banco de dados, os nomes dos atributos e dos elementos do diagrama de atualização poderão ser arbitrários e o esquema fará o mapeamento necessário desses nomes para colunas e tabelas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="94072-107">Instead, if you specify a separate mapping schema that maps the elements and attributes in an updategram to the database tables and columns, your updategram element and attribute names can be arbitrary, and the schema does necessary mapping of these names to the database tables and columns.</span></span> <span data-ttu-id="94072-108">Assim, as informações do banco de dados não serão expostas em um diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="94072-108">Thus, the database information is not exposed in an updategram.</span></span>  
  
-   <span data-ttu-id="94072-109">Não permita que os usuários criem e executem seus diagramas de atualização.</span><span class="sxs-lookup"><span data-stu-id="94072-109">Do not allow users to create and execute their updategrams.</span></span> <span data-ttu-id="94072-110">É recomendável que os diagramas de atualização existam como modelos em um servidor, em vez de serem criados dinamicamente em aplicativos do tipo ASP, o que poderia colocar os dados do banco de dados em risco.</span><span class="sxs-lookup"><span data-stu-id="94072-110">It is recommended having updategrams reside as templates on a server rather than creating them dynamically in ASP-type applications, which could put the data in the database at risk.</span></span> <span data-ttu-id="94072-111">Permitir que os usuários acessem os dados somente por meio dos diagramas de atualização fornecidos como modelos poderá eliminar esse risco.</span><span class="sxs-lookup"><span data-stu-id="94072-111">Allowing users to access the data only through the updategrams provided as templates, can eliminate this risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94072-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94072-112">See Also</span></span>  
 [<span data-ttu-id="94072-113">Usando diagramas de atualização para modificar dados no SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="94072-113">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
  
  
