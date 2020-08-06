---
title: Exemplo de arquivo de entrada XML com DTA (configuração especificada pelo usuário) | Microsoft Docs
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
ms.assetid: b29c9716-e5c3-4003-9efb-3ade2197b630
author: stevestein
ms.author: sstein
ms.openlocfilehash: 121972518aa114e16cc81517d52a9d9656b067c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576091"
---
# <a name="xml-input-file-sample-with-user-specified-configuration-dta"></a><span data-ttu-id="0dc61-102">Exemplo de arquivo de entrada XML com configuração especificada pelo usuário (DTA)</span><span class="sxs-lookup"><span data-stu-id="0dc61-102">XML Input File Sample with User-specified Configuration (DTA)</span></span>
  <span data-ttu-id="0dc61-103">Copie e cole este exemplo de um arquivo de entrada XML que especifica uma configuração especificada pelo usuário com o elemento **Configuration** em seu editor XML ou editor de texto favorito.</span><span class="sxs-lookup"><span data-stu-id="0dc61-103">Copy and paste this sample of an XML input file that specifies a user-specified configuration with the **Configuration** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="0dc61-104">Isso permite realizar uma análise hipotética.</span><span class="sxs-lookup"><span data-stu-id="0dc61-104">This enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="0dc61-105">A análise hipotética envolve o uso do elemento **Configuration** para especificar um conjunto de estruturas de design físico hipotéticas para o banco de dados que você deseja ajustar.</span><span class="sxs-lookup"><span data-stu-id="0dc61-105">"What-if" analysis involves using the **Configuration** element to specify a set of hypothetical physical design structures for the database you want to tune.</span></span> <span data-ttu-id="0dc61-106">Então você usa o Orientador de Otimização do Mecanismo de Banco de Dados para analisar os efeitos de executar uma carga de trabalho em relação a essa configuração hipotética para descobrir se ela melhorará o desempenho de processamento de consulta.</span><span class="sxs-lookup"><span data-stu-id="0dc61-106">Then you use Database Engine Tuning Advisor to analyze the effects of running a workload against this hypothetical configuration to find out whether it improves query processing performance.</span></span> <span data-ttu-id="0dc61-107">Esse tipo de análise oferece a vantagem de poder avaliar a nova configuração sem incorrer na sobrecarga da implementação de fato.</span><span class="sxs-lookup"><span data-stu-id="0dc61-107">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="0dc61-108">Se sua configuração hipotética não oferecer a melhora de desempenho desejada, é fácil alterá-la e fazer novas análises até que você alcance a configuração que produza os resultados necessários.</span><span class="sxs-lookup"><span data-stu-id="0dc61-108">If your hypothetical configuration does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="0dc61-109">Depois de copiar esse exemplo em sua ferramenta de edição, substitua os valores especificados para os elementos **Servidor**, **Banco de Dados**, **Esquema**, **Tabela**, **Carga de trabalho**, **Opções de Ajuste**e **Configuração** com aqueles para sua sessão de ajuste específica.</span><span class="sxs-lookup"><span data-stu-id="0dc61-109">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**, and **Configuration** elements with those for your specific tuning session.</span></span> <span data-ttu-id="0dc61-110">Para obter mais informações sobre todos os atributos e elementos filho que podem ser usados com esses elementos, veja a [Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="0dc61-110">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="0dc61-111">O exemplo a segui usa um subconjunto de atributo único disponível e opções de elemento filho.</span><span class="sxs-lookup"><span data-stu-id="0dc61-111">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="0dc61-112">Código</span><span class="sxs-lookup"><span data-stu-id="0dc61-112">Code</span></span>  
 [!code-xml[InputFileSamples#UserSpecifiedConfigInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#userspecifiedconfiginputfile)]  
  
## <a name="comments"></a><span data-ttu-id="0dc61-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="0dc61-113">Comments</span></span>  
  
-   <span data-ttu-id="0dc61-114">A remoção das estruturas de design físico não terá suporte caso você especifique o modo **Absoluto** para o elemento **Configuration** (`Configuration SpecificationMode="Absolute"`).</span><span class="sxs-lookup"><span data-stu-id="0dc61-114">Dropping physical design structures is not supported if you specify the **Absolute** mode for the **Configuration** element (`Configuration SpecificationMode="Absolute"`).</span></span>  
  
-   <span data-ttu-id="0dc61-115">Não é possível criar e remover a mesma estrutura de design físico em qualquer um dos modos (**Relative** ou **Absolute**) do elemento **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="0dc61-115">You cannot create and drop the same physical design structure in either mode (**Relative** or **Absolute**) of the **Configuration** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc61-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0dc61-116">See Also</span></span>  
 <span data-ttu-id="0dc61-117">[Iniciar e usar o Orientador de Otimização do Mecanismo de Banco de Dados](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0dc61-117">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="0dc61-118">[Exibir e trabalhar com a saída do Orientador de Otimização do Mecanismo de Banco de Dados](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0dc61-118">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="0dc61-119">Referência do arquivo de entrada XML &#40;Orientador de Otimização do Mecanismo de Banco de Dados&#41;</span><span class="sxs-lookup"><span data-stu-id="0dc61-119">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
