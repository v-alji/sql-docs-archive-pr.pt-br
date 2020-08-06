---
title: Editor de destino de arquivo bruto (página colunas) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationcolumns.f1
ms.assetid: 37f61d0b-1269-42ee-94ab-011cbaac63e9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a89d8ca46805a23fd03465ed40428081499dccb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679413"
---
# <a name="raw-file-destination-editor-columns-page"></a><span data-ttu-id="5e375-102">Editor de destino Arquivo Bruto (página Colunas)</span><span class="sxs-lookup"><span data-stu-id="5e375-102">Raw File Destination Editor (Columns Page)</span></span>
  <span data-ttu-id="5e375-103">Use o Editor de Destino Arquivo Bruto para configurar o destino Arquivo Bruto para gravar dados brutos em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e375-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="5e375-104">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="5e375-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="5e375-105">Abra o Editor de destino Arquivo Bruto</span><span class="sxs-lookup"><span data-stu-id="5e375-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="5e375-106">Definir as opções na guia de Gerenciador de Conexões</span><span class="sxs-lookup"><span data-stu-id="5e375-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="5e375-107">Definir opções na guia Colunas</span><span class="sxs-lookup"><span data-stu-id="5e375-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a><span data-ttu-id="5e375-108">Abrir o editor de destino arquivo bruto</span><span class="sxs-lookup"><span data-stu-id="5e375-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="5e375-109">Adicione o destino Arquivo Bruto a um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e375-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="5e375-110">Clique com o botão direito do mouse no componente e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5e375-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a><span data-ttu-id="5e375-111">Definir opções na guia Gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="5e375-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="5e375-112">**Modo de acesso**</span><span class="sxs-lookup"><span data-stu-id="5e375-112">**Access mode**</span></span>  
 <span data-ttu-id="5e375-113">Selecione o modo como o nome de arquivo é especificado.</span><span class="sxs-lookup"><span data-stu-id="5e375-113">Select how the file name is specified.</span></span> <span data-ttu-id="5e375-114">Selecione **Nome de arquivo** para inserir o nome do arquivo e o caminho diretamente de **Nome de arquivo de variável** para especificar uma variável que contenha o nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e375-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="5e375-115">**Nome do arquivo** ou **Nome de variável**</span><span class="sxs-lookup"><span data-stu-id="5e375-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="5e375-116">Insira o nome e o caminho do arquivo bruto ou selecione a variável que contém o nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e375-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="5e375-117">**Opção de gravação**</span><span class="sxs-lookup"><span data-stu-id="5e375-117">**Write option**</span></span>  
 <span data-ttu-id="5e375-118">Selecione o método usado para criar e gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e375-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="5e375-119">**Gerar arquivo bruto inicial**</span><span class="sxs-lookup"><span data-stu-id="5e375-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="5e375-120">Clique no botão para gerar um arquivo bruto vazio que contém somente as colunas (arquivo de somente metadados) sem precisar executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="5e375-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="5e375-121">Você pode apontar a origem Arquivo Bruto para o arquivo somente de metadados.</span><span class="sxs-lookup"><span data-stu-id="5e375-121">You can point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="5e375-122">Quando você clica no botão, uma lista das colunas é exibida.</span><span class="sxs-lookup"><span data-stu-id="5e375-122">When you click the button, a list of the columns appears.</span></span> <span data-ttu-id="5e375-123">Você pode clicar em cancelar e modificar as colunas ou pode clicar em OK para continuar a criação do arquivo.</span><span class="sxs-lookup"><span data-stu-id="5e375-123">You can click cancel and modify the columns or click OK to proceed with creating the file.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="5e375-124">Definir opções na guia colunas</span><span class="sxs-lookup"><span data-stu-id="5e375-124">Set options on the Columns tab</span></span>  
 <span data-ttu-id="5e375-125">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="5e375-125">**Available Input Columns**</span></span>  
 <span data-ttu-id="5e375-126">Selecione uma ou mais colunas de entrada para gravar no arquivo bruto.</span><span class="sxs-lookup"><span data-stu-id="5e375-126">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="5e375-127">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="5e375-127">**Input Column**</span></span>  
 <span data-ttu-id="5e375-128">Uma coluna de entrada é adicionada automaticamente a essa tabela quando você a seleciona em **Colunas de Entrada Disponíveis**; se preferir, selecione a coluna de entrada diretamente nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="5e375-128">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="5e375-129">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="5e375-129">**Output Alias**</span></span>  
 <span data-ttu-id="5e375-130">Especifique um nome alternativo a ser usado para a coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="5e375-130">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e375-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="5e375-131">See Also</span></span>  
 [<span data-ttu-id="5e375-132">Destino do Arquivo Bruto</span><span class="sxs-lookup"><span data-stu-id="5e375-132">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
