---
title: Ferramentas externas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- External Tools dialog box
ms.assetid: d7dae88f-0781-4162-96cd-d3a3a4d82035
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39cd0d139e81c02a7d2a58fae4e74221be7f78e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680742"
---
# <a name="external-tools"></a><span data-ttu-id="490de-102">Ferramentas Externas</span><span class="sxs-lookup"><span data-stu-id="490de-102">External Tools</span></span>
  <span data-ttu-id="490de-103">Use esta caixa de diálogo para adicionar ferramentas externas, como o Gerenciador de Configurações do SQL Server ou o Bloco de Notas, ao menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="490de-103">Use this dialog box to add external tools, such as SQL Server Configuration Manager or Notepad, to the **Tools** menu.</span></span> <span data-ttu-id="490de-104">Adicionar ferramentas externas permite a execução de outros aplicativos facilmente enquanto você trabalha no ambiente do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="490de-104">Adding external tools allows you to easily launch other applications while working in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="490de-105">Você pode especificar argumentos e um diretório de trabalho na execução da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="490de-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="490de-106">Além disso, as saídas de algumas ferramentas podem ser exibidas na janela Saída.</span><span class="sxs-lookup"><span data-stu-id="490de-106">In addition, the outputs from some tools can be displayed in the Output window.</span></span> <span data-ttu-id="490de-107">A caixa de diálogo **Ferramentas Externas** está disponível no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="490de-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="490de-108">Opções</span><span class="sxs-lookup"><span data-stu-id="490de-108">Options</span></span>  
 <span data-ttu-id="490de-109">**Conteúdo do Menu**</span><span class="sxs-lookup"><span data-stu-id="490de-109">**Menu Contents**</span></span>  
 <span data-ttu-id="490de-110">Relaciona os títulos dos itens atuais adicionados ao menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="490de-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="490de-111">Use as setas **Mover para Cima** e **Mover para Baixo** para alterar a ordem dos itens que aparecem no menu.</span><span class="sxs-lookup"><span data-stu-id="490de-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="490de-112">Use o botão **Excluir** para remover um item do menu.</span><span class="sxs-lookup"><span data-stu-id="490de-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="490de-113">**Mover para Cima**</span><span class="sxs-lookup"><span data-stu-id="490de-113">**Move Up**</span></span>  
 <span data-ttu-id="490de-114">Mova a ferramenta selecionada para cima na lista de ferramentas exibida no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="490de-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="490de-115">**Mover para Baixo**</span><span class="sxs-lookup"><span data-stu-id="490de-115">**Move Down**</span></span>  
 <span data-ttu-id="490de-116">Mova a ferramenta selecionada para baixo na lista de ferramentas exibida no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="490de-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="490de-117">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="490de-117">**Add**</span></span>  
 <span data-ttu-id="490de-118">Desmarque as caixas de texto para que você possa especificar uma nova ferramenta.</span><span class="sxs-lookup"><span data-stu-id="490de-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="490de-119">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="490de-119">**Delete**</span></span>  
 <span data-ttu-id="490de-120">Remova a ferramenta ou o comando da lista **Conteúdo do Menu** , bem como do menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="490de-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="490de-121">**Título**</span><span class="sxs-lookup"><span data-stu-id="490de-121">**Title**</span></span>  
 <span data-ttu-id="490de-122">Nome da ferramenta ou do comando que será exibido no submenu **Ferramentas Externas** do menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="490de-122">The name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="490de-123">Coloque um E comercial (&amp;) antes de uma letra no nome da ferramenta para usar essa letra como uma tecla de atalho.</span><span class="sxs-lookup"><span data-stu-id="490de-123">Place an ampersand before a letter in the name of the tool to use that letter as an accelerator key for the tool.</span></span> <span data-ttu-id="490de-124">Por exemplo, `&Spy++` exibiria **Spy++** no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="490de-124">For example, `&Spy++` would display **Spy++** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="490de-125">**Comando**</span><span class="sxs-lookup"><span data-stu-id="490de-125">**Command**</span></span>  
 <span data-ttu-id="490de-126">Especifique o caminho do .exe, .com, .pif, .bat, .cmd ou outro arquivo que você pretende abrir.</span><span class="sxs-lookup"><span data-stu-id="490de-126">Specify the path to the .exe, .com, .pif, .bat, .cmd, or other file that you intend to launch.</span></span> <span data-ttu-id="490de-127">A saída do `.bat`, `.com`e de outros arquivos pode ser exibida na janela Saída se você marcar a caixa de seleção **Usar janela Saída** .</span><span class="sxs-lookup"><span data-stu-id="490de-127">The output from `.bat`, `.com`, and other files can be viewed in the Output window if you select the **Use output window** check box.</span></span>  
  
 <span data-ttu-id="490de-128">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="490de-128">**Arguments**</span></span>  
 <span data-ttu-id="490de-129">Especifique as variáveis que serão passadas à ferramenta quando a ferramenta for selecionada no menu.</span><span class="sxs-lookup"><span data-stu-id="490de-129">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="490de-130">Os argumentos podem especificar valores que são passados à ferramenta ou ao comando quando são iniciados.</span><span class="sxs-lookup"><span data-stu-id="490de-130">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="490de-131">Por exemplo, um valor pode especificar um nome de arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="490de-131">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="490de-132">Use o botão de **Seta** para fazer a seleção em uma lista de argumentos predefinidos.</span><span class="sxs-lookup"><span data-stu-id="490de-132">Use the **Arrow** button to select from a list of predefined arguments.</span></span> <span data-ttu-id="490de-133">Você pode adicionar mais de um argumento.</span><span class="sxs-lookup"><span data-stu-id="490de-133">You can add more than one.</span></span> <span data-ttu-id="490de-134">Para obter uma lista completa de argumentos predefinidos e suas definições, consulte [Arguments for External Tools](external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="490de-134">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](external-tools.md).</span></span> <span data-ttu-id="490de-135">Você também pode inserir argumentos personalizados (por exemplo, opções de prompt de comando), dependendo do comando ou da ferramenta usada.</span><span class="sxs-lookup"><span data-stu-id="490de-135">You can also enter custom arguments (command-prompt switches, for example), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="490de-136">**Diretório inicial**</span><span class="sxs-lookup"><span data-stu-id="490de-136">**Initial directory**</span></span>  
 <span data-ttu-id="490de-137">Especifique o diretório de trabalho da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="490de-137">Specify the working directory of the tool.</span></span> <span data-ttu-id="490de-138">Use o botão de **Seta** para selecionar diretórios.</span><span class="sxs-lookup"><span data-stu-id="490de-138">Use the **Arrow** button to select directories.</span></span> <span data-ttu-id="490de-139">Você pode selecionar mais de um argumento.</span><span class="sxs-lookup"><span data-stu-id="490de-139">You can select more than one.</span></span>  
  
 <span data-ttu-id="490de-140">**Use output Window**</span><span class="sxs-lookup"><span data-stu-id="490de-140">**Use output Window**</span></span>  
 <span data-ttu-id="490de-141">Especifique se os resultados da ferramenta são ou não exibidos na janela Saída.</span><span class="sxs-lookup"><span data-stu-id="490de-141">Specify whether or not results from the tool are displayed in the Output window.</span></span> <span data-ttu-id="490de-142">Essa opção só se encontra disponível para arquivos, como .bat e .com, que normalmente exibem a saída na janela do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="490de-142">This option is only available for files, such as .bat and .com files, that normally display output in the command prompt window.</span></span> <span data-ttu-id="490de-143">Quando habilitada, essa opção facilita o gerenciamento de janelas quando você segue o progresso de uma ferramenta.</span><span class="sxs-lookup"><span data-stu-id="490de-143">When enabled, this option eases window management when you are following the progress of a tool.</span></span>  
  
 <span data-ttu-id="490de-144">**Solicitar argumentos**</span><span class="sxs-lookup"><span data-stu-id="490de-144">**Prompt for arguments**</span></span>  
 <span data-ttu-id="490de-145">Exiba a caixa de diálogo **Argumentos** para permitir a inserção ou edição de valores dos argumentos sempre que você iniciar a ferramenta externa.</span><span class="sxs-lookup"><span data-stu-id="490de-145">Display the **Arguments** dialog box to enable you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="490de-146">**Tratar saída como Unicode**</span><span class="sxs-lookup"><span data-stu-id="490de-146">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="490de-147">Permita que a janela Saída aceite o Unicode.</span><span class="sxs-lookup"><span data-stu-id="490de-147">Allow the Output window to accept Unicode.</span></span>  
  
 <span data-ttu-id="490de-148">**Fechar ao Sair**</span><span class="sxs-lookup"><span data-stu-id="490de-148">**Close On Exit**</span></span>  
 <span data-ttu-id="490de-149">Fecha a janela aberta pela ferramenta quando ela for encerrada.</span><span class="sxs-lookup"><span data-stu-id="490de-149">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="490de-150">Exemplo</span><span class="sxs-lookup"><span data-stu-id="490de-150">Example</span></span>  
  
#### <a name="to-add-sql-server-configuration-manager-to-the-tools-menu"></a><span data-ttu-id="490de-151">Para adicionar o Gerenciador de Configurações do SQL Server ao menu Ferramentas</span><span class="sxs-lookup"><span data-stu-id="490de-151">To add SQL Server Configuration Manager to the Tools menu</span></span>  
  
1.  <span data-ttu-id="490de-152">No menu **Ferramentas** , clique em **Ferramentas Externas**.</span><span class="sxs-lookup"><span data-stu-id="490de-152">On the **Tools** menu, click **External Tools**.</span></span>  
  
2.  <span data-ttu-id="490de-153">Na caixa **Título** , digite **Gerenciador de Configurações do SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="490de-153">In the **Title** box, type **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="490de-154">Na caixa **comando** , digite o caminho para o [!INCLUDE[msCoName](../../includes/msconame-md.md)] executável do console de gerenciamento, como`C:\WINNT\system32\mmc.exe`</span><span class="sxs-lookup"><span data-stu-id="490de-154">In the **Command** box, type the path to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console executable, such as `C:\WINNT\system32\mmc.exe`</span></span>  
  
4.  <span data-ttu-id="490de-155">Na caixa **argumentos** , digite o caminho para o arquivo. msc, como`"C:\WINNT\system32\SQLServerManager.msc"`</span><span class="sxs-lookup"><span data-stu-id="490de-155">In the **Arguments** box, type the path to the .msc file, such as `"C:\WINNT\system32\SQLServerManager.msc"`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="490de-156">Veja as propriedades do atalho do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] no menu **Iniciar** para confirmar o local dos arquivos em seu computador.</span><span class="sxs-lookup"><span data-stu-id="490de-156">View the properties of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] shortcut on the **Start** menu to confirm the location of the files on your computer.</span></span>  
