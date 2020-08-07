---
title: Exemplos de componentes Script adicionais | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: 849dd38a-abb5-4702-a413-882aae3980a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 897ca075674f5c3dbaf355390fe8346580bf638a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575226"
---
# <a name="additional-script-component-examples"></a><span data-ttu-id="68a71-102">Exemplos de componentes Script adicionais</span><span class="sxs-lookup"><span data-stu-id="68a71-102">Additional Script Component Examples</span></span>
  <span data-ttu-id="68a71-103">O componente de Script é uma ferramenta configurável que pode ser usada no fluxo de dados de um pacote para atender a quase todos os requisitos não atendidos pelas fontes, transformações e destinos incluídos no [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68a71-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="68a71-104">Essa seção contém amostras de código do componente Script que demonstram os vários tipos de funcionalidade disponíveis.</span><span class="sxs-lookup"><span data-stu-id="68a71-104">This section contains Script component code samples that demonstrate the various types of functionality that are available.</span></span>  
  
 <span data-ttu-id="68a71-105">Para obter amostras de como configurar o componente Script de forma básica como origem, transformação ou destino, consulte [Desenvolver tipos específicos de componentes Script](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="68a71-105">For samples that demonstrate how to configure the Script component as a basic source, transformation, or destination, see [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68a71-106">Para criar componentes com maior facilidade de reutilização em várias tarefas de Fluxo de Dados e em vários pacotes, procure utilizar o código desses exemplos de componentes Script como o ponto inicial de componentes de fluxo de dados personalizados.</span><span class="sxs-lookup"><span data-stu-id="68a71-106">If you want to create components that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in these Script component samples as the starting point for custom data flow components.</span></span> <span data-ttu-id="68a71-107">Para obter mais informações, consulte [Desenvolvendo um componente de fluxo de dados personalizado](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="68a71-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68a71-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="68a71-108">In This Section</span></span>  
 [<span data-ttu-id="68a71-109">Simulando uma saída de erro para o componente Script</span><span class="sxs-lookup"><span data-stu-id="68a71-109">Simulating an Error Output for the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md)  
 <span data-ttu-id="68a71-110">O componente Script não dá suporte a uma saída de erro padrão, mas você pode simular uma saída de erro padrão com pouca configuração e codificação adicional.</span><span class="sxs-lookup"><span data-stu-id="68a71-110">The Script component does not support a standard error output, but you can simulate a standard error output with very little additional configuration and coding.</span></span>  
  
 [<span data-ttu-id="68a71-111">Aprimorando uma saída de erro com o componente Script</span><span class="sxs-lookup"><span data-stu-id="68a71-111">Enhancing an Error Output with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/enhancing-an-error-output-with-the-script-component.md)  
 <span data-ttu-id="68a71-112">Explica e demonstra como incluir informações adicionais em uma saída de erro padrão usando o componente Script.</span><span class="sxs-lookup"><span data-stu-id="68a71-112">Explains and demonstrates how to add additional information to a standard error output by using the Script component.</span></span>  
  
 [<span data-ttu-id="68a71-113">Criando um destino ODBC com o componente Script</span><span class="sxs-lookup"><span data-stu-id="68a71-113">Creating an ODBC Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/creating-an-odbc-destination-with-the-script-component.md)  
 <span data-ttu-id="68a71-114">Explica e demonstra como criar um destino de fluxo de dados ODBC usando o componente Script.</span><span class="sxs-lookup"><span data-stu-id="68a71-114">Explains and demonstrates how to create an ODBC data flow destination by using the Script component.</span></span>  
  
 [<span data-ttu-id="68a71-115">Analisando formatos de arquivo de texto fora do padrão com o componente Script</span><span class="sxs-lookup"><span data-stu-id="68a71-115">Parsing Non-Standard Text File Formats with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/parsing-non-standard-text-file-formats-with-the-script-component.md)  
 <span data-ttu-id="68a71-116">Explica e demonstra como analisar dois formatos diferentes de arquivo de texto não padronizados em tabelas de destino.</span><span class="sxs-lookup"><span data-stu-id="68a71-116">Explains and demonstrates how to parse two different non-standard text file formats into destination tables.</span></span>  
  
<span data-ttu-id="68a71-117">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="68a71-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="68a71-118">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="68a71-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="68a71-119">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="68a71-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="68a71-120">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="68a71-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
