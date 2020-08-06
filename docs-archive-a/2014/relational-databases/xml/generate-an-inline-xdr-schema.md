---
title: Gerar um esquema XDR embutido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XDR schemas [SQL Server]
- inline XDR schema generation [SQL Server]
- XMLDATA option
- FOR XML clause, inline XDR schema generation
ms.assetid: 2a40d617-9724-4f7d-80a4-a85c702f14d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e2bb7b4b482b79ab5550540dd5b24ffdd8d6636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686183"
---
# <a name="generate-an-inline-xdr-schema"></a><span data-ttu-id="703ff-102">Gerar um esquema XDR embutido</span><span class="sxs-lookup"><span data-stu-id="703ff-102">Generate an Inline XDR Schema</span></span>
  <span data-ttu-id="703ff-103">A diretiva **XMLDATA** no FOR XML retorna um esquema XDR embutido junto com o resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="703ff-103">The **XMLDATA** directive in FOR XML returns an inline XDR schema together with the query result.</span></span> <span data-ttu-id="703ff-104">No entanto, o esquema XDR não oferece suporte a todos os novos tipos de dados e outras melhorias apresentadas no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="703ff-104">However, the XDR schema does not support all the new data types and other enhancements introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="703ff-105">Em vez disso, é possível solicitar um esquema XSD embutido usando [a diretiva XMLSCHEMA](generate-an-inline-xsd-schema.md).</span><span class="sxs-lookup"><span data-stu-id="703ff-105">Instead, you can request an inline XSD schema by using [the XMLSCHEMA directive](generate-an-inline-xsd-schema.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="703ff-106">A diretiva XMLDATA para a opção FOR XML foi preterida.</span><span class="sxs-lookup"><span data-stu-id="703ff-106">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="703ff-107">Use geração de XSD no caso dos modos RAW e AUTO.</span><span class="sxs-lookup"><span data-stu-id="703ff-107">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="703ff-108">Não há substituição para a diretiva XMLDATA no modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="703ff-108">There is no replacement for the XMLDATA directive in EXPLICIT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="703ff-109">Também observe o seguinte sobre o suporte ao esquema XDR:</span><span class="sxs-lookup"><span data-stu-id="703ff-109">Also note the following about the inline XDR schema support:</span></span>  
  
-   <span data-ttu-id="703ff-110">Se o resultado da consulta FOR XML incluir colunas de tipo **xml** e você solicitar um esquema XDR embutido, será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="703ff-110">If the FOR XML query result includes columns of **xml** type and you request an inline XDR schema, an error is returned.</span></span> <span data-ttu-id="703ff-111">O XDR embutido não oferece suporte a esses tipos.</span><span class="sxs-lookup"><span data-stu-id="703ff-111">Inline XDR does not support these types.</span></span>  
  
-   <span data-ttu-id="703ff-112">Os tipos **(n)varchar(max)** e **(n)varbinary(max)** serão mapeados para **(n)varchar(n)** e **varbinary(n)** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="703ff-112">The **(n)varchar(max)** and **(n)varbinary(max)** types will be mapped to **(n)varchar(n)** and **varbinary(n)**, respectively.</span></span>  
  
-   <span data-ttu-id="703ff-113">Quando o modo de compatibilidade é definido como 90 ou superior, os valores **timestamp** são considerados como dados **varbinary(8)** , são tratados como dados binários e retornados no resultado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="703ff-113">When compatibility mode is set to 90 or higher, **timestamp** values are considered as **varbinary(8)** data, are treated like binary data, and are returned in the result as follows:</span></span>  
  
    -   <span data-ttu-id="703ff-114">A codificação de Base 64 é usada quando **binary base64** é especificado.</span><span class="sxs-lookup"><span data-stu-id="703ff-114">Base 64 encoding is used when **binary base64** is specified.</span></span>  
  
    -   <span data-ttu-id="703ff-115">A codificação de URL é usada no modo AUTO quando **binary base64** não é especificado.</span><span class="sxs-lookup"><span data-stu-id="703ff-115">URL encoding is used in AUTO mode when **binary base64** is not specified.</span></span>  
  
  
