---
title: Destino de arquivo simples | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledest.f1
helpviewer_keywords:
- flat files
- Flat File destination
- text file writing [Integration Services]
- destinations [Integration Services], Flat File
ms.assetid: e0d6e356-8db4-48aa-ba66-029397f98f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a961b7528b13a4eaa3297343e91f1deaf2fa3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685855"
---
# <a name="flat-file-destination"></a><span data-ttu-id="30dd3-102">Destino de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="30dd3-102">Flat File Destination</span></span>
  <span data-ttu-id="30dd3-103">O destino de Arquivo Simples grava dados em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="30dd3-103">The Flat File destination writes data to a text file.</span></span> <span data-ttu-id="30dd3-104">O arquivo de texto pode ser em formato delimitado, de largura fixa, largura fixa com delimitador de linha ou com imperfeição à direita.</span><span class="sxs-lookup"><span data-stu-id="30dd3-104">The text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="30dd3-105">Você pode configurar o destino de arquivo simples das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="30dd3-105">You can configure the Flat File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="30dd3-106">Forneça um bloco de texto que é inserido no arquivo antes de qualquer dado ser escrito.</span><span class="sxs-lookup"><span data-stu-id="30dd3-106">Provide a block of text that is inserted in the file before any data is written.</span></span> <span data-ttu-id="30dd3-107">O texto pode fornecer informações como cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="30dd3-107">The text can provide information such as column headings.</span></span>  
  
-   <span data-ttu-id="30dd3-108">Especifique se os dados devem ser substituídos em um arquivo de destino que tenha o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="30dd3-108">Specify whether to overwrite a data in a destination file that has the same name.</span></span>  
  
 <span data-ttu-id="30dd3-109">Esse destino utiliza um gerente de conexões de arquivo simples para acessar o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="30dd3-109">This destination uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="30dd3-110">Ao definir propriedades no gerenciador de conexões de arquivo simples que o arquivo simples usa, você pode especificar como o destino do arquivo simples formata e escreve o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="30dd3-110">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="30dd3-111">Quando você configura o gerenciador de conexões de arquivo simples, você especifica informações sobre o arquivo e sobre cada coluna do arquivo.</span><span class="sxs-lookup"><span data-stu-id="30dd3-111">When you configure the Flat File connection manager, you specify information about the file and about each column in the file.</span></span> <span data-ttu-id="30dd3-112">Por exemplo, pode-se especificar os caracteres que delimitam colunas e linhas no arquivo e especificar o tipo de dados e o comprimento de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="30dd3-112">For example, you specify the characters that delimit columns and rows in the file, and you specify the data type and the length of each column.</span></span> <span data-ttu-id="30dd3-113">Para obter mais informações, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="30dd3-113">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="30dd3-114">O destino de arquivo simples inclui a propriedade personalizada Header.</span><span class="sxs-lookup"><span data-stu-id="30dd3-114">The Flat File destination includes the Header custom property.</span></span> <span data-ttu-id="30dd3-115">Essa propriedade pode ser atualizada por uma expressão de propriedade quando o pacote é carregado.</span><span class="sxs-lookup"><span data-stu-id="30dd3-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="30dd3-116">Para obter mais informações, consulte [Expressões do Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Usar expressões de propriedade em pacotes](../expressions/use-property-expressions-in-packages.md) e [Propriedades personalizadas de arquivo simples](flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="30dd3-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [Flat File Custom Properties](flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="30dd3-117">Esse destino tem uma saída.</span><span class="sxs-lookup"><span data-stu-id="30dd3-117">This destination has one output.</span></span> <span data-ttu-id="30dd3-118">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="30dd3-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-destination"></a><span data-ttu-id="30dd3-119">Configuração do destino de Arquivo Simples</span><span class="sxs-lookup"><span data-stu-id="30dd3-119">Configuration of the Flat File Destination</span></span>  
 <span data-ttu-id="30dd3-120">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="30dd3-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="30dd3-121">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Fonte de Arquivo Simples**, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="30dd3-121">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="30dd3-122">Editor de Destino de Arquivo Simples &#40;Página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="30dd3-122">Flat File Destination Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="30dd3-123">Editor de Destino de Arquivo Simples &#40;Página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="30dd3-123">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../flat-file-destination-editor-mappings-page.md)  
  
 <span data-ttu-id="30dd3-124">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="30dd3-124">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="30dd3-125">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="30dd3-125">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="30dd3-126">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="30dd3-126">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="30dd3-127">Propriedades personalizadas de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="30dd3-127">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="30dd3-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="30dd3-128">Related Tasks</span></span>  
 <span data-ttu-id="30dd3-129">Para obter informações sobre como definir as propriedades do componente de fluxo de dados, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="30dd3-129">For information about how to set the properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30dd3-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="30dd3-130">See Also</span></span>  
 <span data-ttu-id="30dd3-131">[Fonte de Arquivo Simples](flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="30dd3-131">[Flat File Source](flat-file-source.md) </span></span>  
 [<span data-ttu-id="30dd3-132">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="30dd3-132">Data Flow</span></span>](data-flow.md)  
  
  
