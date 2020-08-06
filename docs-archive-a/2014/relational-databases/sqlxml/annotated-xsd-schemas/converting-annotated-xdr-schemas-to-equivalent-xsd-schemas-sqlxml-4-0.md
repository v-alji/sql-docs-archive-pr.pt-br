---
title: Convertendo esquemas XDR anotados em esquemas XSD equivalentes (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XDR schemas, converting schemas
- annotated XSD schemas, converting schemas
- XDR to XSD Converter tool [SQLXML]
- XDR schemas [SQLXML], converting
- converting annotated schemas
- mapping schema [SQLXML], conversions
- XSD schemas [SQLXML], converting schemas
ms.assetid: 151c94a8-66d3-4c46-a5ff-a22df456940a
author: rothja
ms.author: jroth
ms.openlocfilehash: c36eb17aacb61a47fad0f389de9a3c216202827d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575731"
---
# <a name="converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-40"></a><span data-ttu-id="17013-102">Convertendo esquemas XDR anotados a esquemas XSD equivalentes (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="17013-102">Converting Annotated XDR Schemas to Equivalent XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="17013-103">A linguagem XSD é a sucessora da linguagem XDR.</span><span class="sxs-lookup"><span data-stu-id="17013-103">The XML Schema Definition (XSD) language is the successor to the XML-Data Reduced (XDR) schema definition language.</span></span> <span data-ttu-id="17013-104">Com a introdução do suporte a XSD no SQLXML 4.0 do [!INCLUDE[msCoName](../../../includes/msconame-md.md)], supõe-se a criação de novos esquemas anotados usando XSD.</span><span class="sxs-lookup"><span data-stu-id="17013-104">With the introduction of XSD support in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, it is assumed that new annotated schemas are created using XSD.</span></span> <span data-ttu-id="17013-105">O SQLXML 4.0 inclui uma ferramenta de conversão de XDR para XSD projetada para ajudá-lo a converter os esquemas XDR anotados em esquemas XSD equivalentes.</span><span class="sxs-lookup"><span data-stu-id="17013-105">SQLXML 4.0 includes an XDR to XSD converter tool that is designed to help you convert your existing annotated XDR schemas to equivalent XSD schemas.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="17013-106">Só use essa ferramenta quando quiser converter esquemas XDR anotados em XSD a serem usados o com SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="17013-106">Use this tool only when you want to convert annotated XDR schemas to XSD for use with SQLXML 4.0.</span></span> <span data-ttu-id="17013-107">Não se trata de uma ferramenta de conversão de XDR em XSD de uso geral.</span><span class="sxs-lookup"><span data-stu-id="17013-107">This is not a general purpose XDR to XSD converter tool.</span></span> <span data-ttu-id="17013-108">Os esquemas XSD convertidos talvez não se comportem da mesma forma que os esquemas XDR originais quando usados em outros ambientes.</span><span class="sxs-lookup"><span data-stu-id="17013-108">The converted XSD schemas may not behave the same as the original XDR schemas when used in other environments.</span></span>  
  
 <span data-ttu-id="17013-109">Caso o arquivo XDR de entrada especifique a codificação na declaração XML, esta se torna a codificação do arquivo de saída XSD gerado.</span><span class="sxs-lookup"><span data-stu-id="17013-109">If the input XDR file specifies the encoding within the XML declaration, this becomes the encoding of the XSD output file that is generated.</span></span>  
  
 <span data-ttu-id="17013-110">A ferramenta de conversão (Cvtschema.exe) é instalada na pasta Arquivos de Programa\SQLXML 4.0\bin, sendo executada no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="17013-110">The converter tool (Cvtschema.exe) is installed in the Program Files\SQLXML 4.0\bin folder and is executed at the command prompt.</span></span>  
  
 <span data-ttu-id="17013-111">Esta é a sintaxe geral:</span><span class="sxs-lookup"><span data-stu-id="17013-111">This is the general syntax:</span></span>  
  
```  
cvtschema XDRFileName, [-y], [-w] [-?]  
```  
  
 <span data-ttu-id="17013-112">Em que:</span><span class="sxs-lookup"><span data-stu-id="17013-112">Where:</span></span>  
  
 <span data-ttu-id="17013-113">XDRFileName</span><span class="sxs-lookup"><span data-stu-id="17013-113">XDRFileName</span></span>  
 <span data-ttu-id="17013-114">É o nome do arquivo XDR a ser convertido em XSD.</span><span class="sxs-lookup"><span data-stu-id="17013-114">Is the name of the XDR file that is to be converted to XSD.</span></span> <span data-ttu-id="17013-115">A ferramenta lê o arquivo XDR de entrada e cria um arquivo de saída XSD no diretório funcional atual.</span><span class="sxs-lookup"><span data-stu-id="17013-115">The tool reads the input XDR file and creates an XSD output file in the current working directory.</span></span> <span data-ttu-id="17013-116">Caso o arquivo de entrada tenha uma extensão .xdr ou .xml, o arquivo XSD de saída é criado com o mesmo nome, mas com uma extensão .xsd.</span><span class="sxs-lookup"><span data-stu-id="17013-116">If the input file has an .xdr or .xml extension, the output XSD file is created with the same name but with an .xsd extension.</span></span> <span data-ttu-id="17013-117">Caso a extensão do arquivo de entrada seja diferente de .xdr ou .xml (ou caso a extensão esteja ausente), o arquivo de saída é criado com o mesmo nome, e a extensão .xsd é acrescentada ao nome do arquivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="17013-117">If the input file extension is other than .xml or .xdr (or if the extension is missing), the output file is created with the same name and the .xsd extension is appended to the input file name.</span></span> <span data-ttu-id="17013-118">Por exemplo, caso o nome de arquivo XDR de entrada seja SampleFile.abc, o XSD resultante é salvo como SampleFile.abc.xsd.</span><span class="sxs-lookup"><span data-stu-id="17013-118">For example, if the input XDR file name is SampleFile.abc, the resulting XSD is saved as SampleFile.abc.xsd.</span></span>  
  
 <span data-ttu-id="17013-119">-y</span><span class="sxs-lookup"><span data-stu-id="17013-119">-y</span></span>  
 <span data-ttu-id="17013-120">(Opcional) Substitui o arquivo XSD existente pelo arquivo XSD gerado pela ferramenta de conversão.</span><span class="sxs-lookup"><span data-stu-id="17013-120">(Optional) Overwrites the existing XSD file with the XSD file that is generated by the converter tool.</span></span> <span data-ttu-id="17013-121">Caso o sinalizador não seja especificado, a ferramenta pede para que você opte por substituir o arquivo existente XSD e lhe dá a opção de alterar o nome do arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="17013-121">If the flag is not specified, the tool prompts you to specify whether you want to overwrite the existing XSD file and gives you the option to change the output file name.</span></span>  
  
 <span data-ttu-id="17013-122">-w</span><span class="sxs-lookup"><span data-stu-id="17013-122">-w</span></span>  
 <span data-ttu-id="17013-123">(Opcional) Retorna advertências não fatais geradas no processo de conversão pela ferramenta.</span><span class="sxs-lookup"><span data-stu-id="17013-123">(Optional) Returns nonfatal warnings that are generated in the conversion process by the tool.</span></span> <span data-ttu-id="17013-124">Por padrão, a ferramenta só exibe mensagens de erros fatais.</span><span class="sxs-lookup"><span data-stu-id="17013-124">By default, the tool displays messages only for fatal errors.</span></span>  
  
 <span data-ttu-id="17013-125">-?</span><span class="sxs-lookup"><span data-stu-id="17013-125">-?</span></span>  
 <span data-ttu-id="17013-126">Retorna uma lista de opções que é possível especificar com `cvtschema`, além de uma explicação.</span><span class="sxs-lookup"><span data-stu-id="17013-126">Returns a list of options that you can specify with `cvtschema`, along with an explanation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17013-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="17013-127">See Also</span></span>  
 <span data-ttu-id="17013-128">[Mapeando tipos de dados XSD para tipos de dados XPath &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="17013-128">[Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="17013-129">Anotações XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="17013-129">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml-annotated-xsd-schemas-using/xsd-annotations-sqlxml-4-0.md)  
  
  
