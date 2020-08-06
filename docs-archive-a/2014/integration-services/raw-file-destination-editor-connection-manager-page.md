---
title: Editor de destino de arquivo bruto (página Gerenciador de conexões) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationconnectionmanager.f1
ms.assetid: a0ec9643-3b44-4467-b855-f45ae4794f7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a693591921a5669eb9bc8160f0be076ab4d6869b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679412"
---
# <a name="raw-file-destination-editor-connection-manager-page"></a><span data-ttu-id="811b3-102">Editor de destino Arquivo Bruto (página Gerenciador de Conexões)</span><span class="sxs-lookup"><span data-stu-id="811b3-102">Raw File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="811b3-103">Use o Editor de Destino Arquivo Bruto para configurar o destino Arquivo Bruto para gravar dados brutos em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="811b3-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="811b3-104">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="811b3-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="811b3-105">Abra o Editor de destino Arquivo Bruto</span><span class="sxs-lookup"><span data-stu-id="811b3-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="811b3-106">Definir as opções na guia de Gerenciador de Conexões</span><span class="sxs-lookup"><span data-stu-id="811b3-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="811b3-107">Definir opções na guia Colunas</span><span class="sxs-lookup"><span data-stu-id="811b3-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a><span data-ttu-id="811b3-108">Abrir o editor de destino arquivo bruto</span><span class="sxs-lookup"><span data-stu-id="811b3-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="811b3-109">Adicione o destino Arquivo Bruto a um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="811b3-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="811b3-110">Clique com o botão direito do mouse no componente e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="811b3-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a><span data-ttu-id="811b3-111">Definir opções na guia Gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="811b3-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="811b3-112">**Modo de acesso**</span><span class="sxs-lookup"><span data-stu-id="811b3-112">**Access mode**</span></span>  
 <span data-ttu-id="811b3-113">Selecione o modo como o nome de arquivo é especificado.</span><span class="sxs-lookup"><span data-stu-id="811b3-113">Select how the file name is specified.</span></span> <span data-ttu-id="811b3-114">Selecione **Nome de arquivo** para inserir o nome do arquivo e o caminho diretamente de **Nome de arquivo de variável** para especificar uma variável que contenha o nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="811b3-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="811b3-115">**Nome do arquivo** ou **Nome de variável**</span><span class="sxs-lookup"><span data-stu-id="811b3-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="811b3-116">Insira o nome e o caminho do arquivo bruto ou selecione a variável que contém o nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="811b3-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="811b3-117">**Opção de gravação**</span><span class="sxs-lookup"><span data-stu-id="811b3-117">**Write option**</span></span>  
 <span data-ttu-id="811b3-118">Selecione o método usado para criar e gravar no arquivo.</span><span class="sxs-lookup"><span data-stu-id="811b3-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="811b3-119">**Gerar arquivo bruto inicial**</span><span class="sxs-lookup"><span data-stu-id="811b3-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="811b3-120">Clique no botão para gerar um arquivo bruto vazio que contém somente as colunas (arquivo de somente metadados) sem precisar executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="811b3-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="811b3-121">O arquivo contém as colunas que você selecionou na página **Colunas** do **Editor de destino Arquivo Bruto**.</span><span class="sxs-lookup"><span data-stu-id="811b3-121">The file contains the columns that you selected on the **Columns** page of the **Raw File Destination Editor**.</span></span> <span data-ttu-id="811b3-122">Você pode apontar a fonte Arquivo Bruto para esse arquivo somente de metadados.</span><span class="sxs-lookup"><span data-stu-id="811b3-122">You can point the Raw File source to this metadata-only file.</span></span>  
  
 <span data-ttu-id="811b3-123">Quando você clica em **Gerar arquivo bruto inicial**, uma caixa de mensagem aparece.</span><span class="sxs-lookup"><span data-stu-id="811b3-123">When you click **Generate initial raw file**, a message box appears.</span></span> <span data-ttu-id="811b3-124">Clique em **OK** para continuar a criar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="811b3-124">Click **OK** to proceed with creating the file.</span></span> <span data-ttu-id="811b3-125">Clique em **Cancelamento** para selecionar uma lista diferente de colunas na página de **Colunas** .</span><span class="sxs-lookup"><span data-stu-id="811b3-125">Click **Cancel** to select a different list of columns on the **Columns** page.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="811b3-126">Definir opções na guia colunas</span><span class="sxs-lookup"><span data-stu-id="811b3-126">Set options on the Columns tab</span></span>  
 <span data-ttu-id="811b3-127">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="811b3-127">**Available Input Columns**</span></span>  
 <span data-ttu-id="811b3-128">Selecione uma ou mais colunas de entrada para gravar no arquivo bruto.</span><span class="sxs-lookup"><span data-stu-id="811b3-128">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="811b3-129">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="811b3-129">**Input Column**</span></span>  
 <span data-ttu-id="811b3-130">Uma coluna de entrada é adicionada automaticamente a essa tabela quando você a seleciona em **Colunas de Entrada Disponíveis**; se preferir, selecione a coluna de entrada diretamente nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="811b3-130">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="811b3-131">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="811b3-131">**Output Alias**</span></span>  
 <span data-ttu-id="811b3-132">Especifique um nome alternativo a ser usado para a coluna de saída.</span><span class="sxs-lookup"><span data-stu-id="811b3-132">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="811b3-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="811b3-133">See Also</span></span>  
 [<span data-ttu-id="811b3-134">Destino do Arquivo Bruto</span><span class="sxs-lookup"><span data-stu-id="811b3-134">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
