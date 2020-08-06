---
title: O elemento &lt;xsd:redefine&gt; | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce439e81cf87e97b4afe6e25a201e1ab0cb2a458
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682181"
---
# <a name="the-ltxsdredefinegt-element"></a><span data-ttu-id="5fc2c-102">O elemento &lt;xsd:redefine&gt;</span><span class="sxs-lookup"><span data-stu-id="5fc2c-102">The &lt;xsd:redefine&gt; Element</span></span>
  <span data-ttu-id="5fc2c-103">O elemento **redefine** do W3C XSD fornece suporte para redefinição de componentes de esquema.</span><span class="sxs-lookup"><span data-stu-id="5fc2c-103">The W3C XSD **redefine** element provides support for redefining schema components.</span></span> <span data-ttu-id="5fc2c-104">No entanto, o suporte para essa diretiva é potencialmente dispendioso para o desempenho e também requer que a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalidação de todas as instâncias do `xml` tipo de dados associadas ao esquema redefinido.</span><span class="sxs-lookup"><span data-stu-id="5fc2c-104">However, support for this directive is potentially costly to performance and also requires that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalidate all instances of the `xml` data type associated with the redefined schema.</span></span> <span data-ttu-id="5fc2c-105">Portanto o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não oferece suporte a esse elemento.</span><span class="sxs-lookup"><span data-stu-id="5fc2c-105">Therefore, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support this element.</span></span> <span data-ttu-id="5fc2c-106">Esquemas XML que incluem o elemento **\<xsd:redefine>** são rejeitados pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="5fc2c-106">XML schemas that include the **\<xsd:redefine>** element are rejected by the server.</span></span>  
  
 <span data-ttu-id="5fc2c-107">Para atualizar um esquema ou seus componentes, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5fc2c-107">To update a schema or its components, you can do the following instead:</span></span>  
  
1.  <span data-ttu-id="5fc2c-108">Crie uma nova coleção de esquema XML com os componentes do esquema modificado.</span><span class="sxs-lookup"><span data-stu-id="5fc2c-108">Create a new XML Schema collection with the modified schema components.</span></span>  
  
2.  <span data-ttu-id="5fc2c-109">Digite novamente todos os `xml` tipos de dados (XML DT) que usam a coleção de esquema XML a ser redefinida para usar a nova coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="5fc2c-109">Retype all `xml` data types (XML DT) that use the XML Schema collection to be redefined to use the new XML Schema collection instead.</span></span> <span data-ttu-id="5fc2c-110">Para isso, use a opção ALTER COLUMN do comando ALTER TABLE para redefinir o tipo das colunas ou altere as restrições da coleção de esquema XML sobre variáveis ou parâmetros.</span><span class="sxs-lookup"><span data-stu-id="5fc2c-110">To do this, use the ALTER COLUMN option of the ALTER TABLE command for retyping columns, or change the XML Schema collection constraints on variables or parameters.</span></span>  
  
3.  <span data-ttu-id="5fc2c-111">Descarte a versão antiga da coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="5fc2c-111">Drop the old version of the XML Schema collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc2c-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5fc2c-112">See Also</span></span>  
 [<span data-ttu-id="5fc2c-113">Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor</span><span class="sxs-lookup"><span data-stu-id="5fc2c-113">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
