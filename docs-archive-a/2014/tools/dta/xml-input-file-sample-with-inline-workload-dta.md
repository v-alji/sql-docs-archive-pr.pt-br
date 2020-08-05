---
title: Exemplo do arquivo de entrada XML com carga de trabalho embutida (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: 7c04fe1d-6669-44a1-8b73-36d469e9b002
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93b2ab4279378b4cd392d97a9b65f299d0e9c6dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572295"
---
# <a name="xml-input-file-sample-with-inline-workload-dta"></a><span data-ttu-id="a9183-102">Amostra do arquivo de entrada XML com carga de trabalho embutida (DTA)</span><span class="sxs-lookup"><span data-stu-id="a9183-102">XML Input File Sample with Inline Workload (DTA)</span></span>
  <span data-ttu-id="a9183-103">Copie e cole esta amostra em um arquivo de entrada XML que especifica uma carga de trabalho com o elemento **EventString** em seu editor de XML ou editor de texto favorito.</span><span class="sxs-lookup"><span data-stu-id="a9183-103">Copy and paste this sample of an XML input file that specifies a workload with the **EventString** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="a9183-104">Você pode usar o elemento **EventString** para especificar uma carga de trabalho de script [!INCLUDE[tsql](../../includes/tsql-md.md)] no arquivo de entrada XML em vez de usar um arquivo de carga de trabalho separado.</span><span class="sxs-lookup"><span data-stu-id="a9183-104">You can use the **EventString** element to specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload in the XML input file instead of using a separate workload file.</span></span> <span data-ttu-id="a9183-105">Depois de copiar esta amostra na ferramenta de edição, substitua os valores especificados dos elementos **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**e **TuningOptions** pelos valores de sua sessão de ajuste específica.</span><span class="sxs-lookup"><span data-stu-id="a9183-105">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**, and **TuningOptions** elements with those for your specific tuning session.</span></span> <span data-ttu-id="a9183-106">Para obter mais informações sobre todos os atributos e elementos filho que podem ser usados com esses elementos, veja a [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="a9183-106">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="a9183-107">O exemplo a segui usa um subconjunto de atributo único disponível e opções de elemento filho.</span><span class="sxs-lookup"><span data-stu-id="a9183-107">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="a9183-108">Código</span><span class="sxs-lookup"><span data-stu-id="a9183-108">Code</span></span>  
 [!code-xml[InputFileSamples#InlineWorkloadInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#inlineworkloadinputfile)]  
  
## <a name="comments"></a><span data-ttu-id="a9183-109">Comentários</span><span class="sxs-lookup"><span data-stu-id="a9183-109">Comments</span></span>  
 <span data-ttu-id="a9183-110">`USE database_name` As instruções podem ser especificadas na carga de trabalho embutida, contida no elemento **EventString** .</span><span class="sxs-lookup"><span data-stu-id="a9183-110">`USE database_name` statements can be specified in the inline workload that is contained in the **EventString** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9183-111">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a9183-111">See Also</span></span>  
 <span data-ttu-id="a9183-112">[Iniciar e usar o Orientador de Otimização do Mecanismo de Banco de Dados](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="a9183-112">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="a9183-113">[Exibir e trabalhar com a saída do Orientador de Otimização do Mecanismo de Banco de Dados](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="a9183-113">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="a9183-114">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="a9183-114">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
