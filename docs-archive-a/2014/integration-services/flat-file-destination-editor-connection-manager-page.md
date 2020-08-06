---
title: Editor de destino de arquivo simples (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledestadapter.connection.f1
helpviewer_keywords:
- Flat File Destination Editor
ms.assetid: b01571fa-bc19-4742-8eed-ac163172a919
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6997b72851c2b7bfc56445e6ddb01cfe6e9b04cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570154"
---
# <a name="flat-file-destination-editor-connection-manager-page"></a><span data-ttu-id="b2463-102">Editor de Destino de Arquivo Simples (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="b2463-102">Flat File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="b2463-103">Use a página do **Gerenciador de Conexões** da caixa de diálogo do **Editor de Destino de Arquivo Simples** para selecionar a conexão de arquivo simples do destino e especificar se irá substituir ou anexar ao arquivo de destino existente.</span><span class="sxs-lookup"><span data-stu-id="b2463-103">Use the **Connection Manager** page of the **Flat File Destination Editor** dialog box to select the flat file connection for the destination, and to specify whether to overwrite or append to the existing destination file.</span></span> <span data-ttu-id="b2463-104">O destino de arquivo simples grava dados em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="b2463-104">The flat file destination writes data to a text file.</span></span> <span data-ttu-id="b2463-105">Esse arquivo de texto pode ser em formato delimitado, de largura fixa, de largura fixa com delimitador de linha ou em formato irregular à direita.</span><span class="sxs-lookup"><span data-stu-id="b2463-105">This text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="b2463-106">Para saber mais sobre o destino de Arquivo Simples, consulte [Flat File Destination](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b2463-106">To learn more about the Flat File destination, see [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b2463-107">Opções</span><span class="sxs-lookup"><span data-stu-id="b2463-107">Options</span></span>  
 <span data-ttu-id="b2463-108">**Gerenciador de conexões de arquivo simples**</span><span class="sxs-lookup"><span data-stu-id="b2463-108">**Flat File connection manager**</span></span>  
 <span data-ttu-id="b2463-109">Selecione um gerenciador de conexões existente usando a caixa de listagem ou crie uma nova conexão clicando em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b2463-109">Select an existing connection manager by using the list box, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="b2463-110">**Novo**</span><span class="sxs-lookup"><span data-stu-id="b2463-110">**New**</span></span>  
 <span data-ttu-id="b2463-111">Crie uma nova conexão utilizando as caixas de diálogo **Formato de Arquivo Simples** e **Editor do Gerenciador de Conexões de Arquivos Simples** .</span><span class="sxs-lookup"><span data-stu-id="b2463-111">Create a new connection by using the **Flat File Format** and **Flat File Connection Manager Editor** dialog boxes.</span></span>  
  
 <span data-ttu-id="b2463-112">Além dos formatos padrão de arquivo simples: delimitado, de largura fixa e irregular à direita, a caixa de diálogo **Formato de Arquivo Simples** tem uma quarta opção, **Largura fixa com delimitadores de linha**.</span><span class="sxs-lookup"><span data-stu-id="b2463-112">In addition to the standard flat file formats of delimited, fixed width, and ragged right, the **Flat File Format** dialog box has a fourth option, **Fixed width with row delimiters**.</span></span> <span data-ttu-id="b2463-113">Esta opção representa um caso especial do formato irregular à direita no qual o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] adiciona uma coluna fictícia como a coluna final de dados.</span><span class="sxs-lookup"><span data-stu-id="b2463-113">This option represents a special case of the ragged-right format in which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] adds a dummy column as the final column of data.</span></span> <span data-ttu-id="b2463-114">Essa coluna fictícia assegura que a coluna final tenha uma largura fixa.</span><span class="sxs-lookup"><span data-stu-id="b2463-114">This dummy column ensures that the final column has a fixed width.</span></span>  
  
 <span data-ttu-id="b2463-115">A opção **Largura fixa com delimitadores de linha** não está disponível no **Editor do Gerenciador de Conexões de Arquivos Simples**.</span><span class="sxs-lookup"><span data-stu-id="b2463-115">The **Fixed width with row delimiters** option is not available in the **Flat File Connection Manager Editor**.</span></span> <span data-ttu-id="b2463-116">Se necessário, você pode emular esta opção no editor.</span><span class="sxs-lookup"><span data-stu-id="b2463-116">If necessary, you can emulate this option in the editor.</span></span> <span data-ttu-id="b2463-117">Para emular esta opção, na página **Geral** do **Editor do Gerenciador de Conexões de Arquivos Simples**, em **Formato**, selecione **Irregular à direita**.</span><span class="sxs-lookup"><span data-stu-id="b2463-117">To emulate this option, on the **General** page of the **Flat File Connection Manager Editor**, for **Format**, select **Ragged right**.</span></span> <span data-ttu-id="b2463-118">Na página **Avançado** do editor, adicione uma nova coluna fictícia como a coluna final de dados.</span><span class="sxs-lookup"><span data-stu-id="b2463-118">Then on the **Advanced** page of the editor, add a new dummy column as the final column of data.</span></span>  
  
 <span data-ttu-id="b2463-119">**Substituir dados no arquivo**</span><span class="sxs-lookup"><span data-stu-id="b2463-119">**Overwrite data in the file**</span></span>  
 <span data-ttu-id="b2463-120">Indique se irá substituir um arquivo existente ou acrescentar dados a ele.</span><span class="sxs-lookup"><span data-stu-id="b2463-120">Indicate whether to overwrite an existing file, or to append data to it.</span></span>  
  
 <span data-ttu-id="b2463-121">**Cabeçalho**</span><span class="sxs-lookup"><span data-stu-id="b2463-121">**Header**</span></span>  
 <span data-ttu-id="b2463-122">Digite um bloco de texto a ser inserido no arquivo antes que qualquer dado seja gravado.</span><span class="sxs-lookup"><span data-stu-id="b2463-122">Type a block of text to insert into the file before any data is written.</span></span> <span data-ttu-id="b2463-123">Use esta opção para incluir informações adicionais, como cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="b2463-123">Use this option to include additional information, such as column headings.</span></span>  
  
 <span data-ttu-id="b2463-124">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="b2463-124">**Preview**</span></span>  
 <span data-ttu-id="b2463-125">Visualize os resultados usando a caixa de diálogo **Exibição de Dados** .</span><span class="sxs-lookup"><span data-stu-id="b2463-125">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="b2463-126">A visualização pode exibir até 200 linhas.</span><span class="sxs-lookup"><span data-stu-id="b2463-126">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2463-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b2463-127">See Also</span></span>  
 <span data-ttu-id="b2463-128">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b2463-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="b2463-129">Editor de Destino de Arquivo Simples &#40;Página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="b2463-129">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/flat-file-destination-editor-mappings-page.md)  
  
  
