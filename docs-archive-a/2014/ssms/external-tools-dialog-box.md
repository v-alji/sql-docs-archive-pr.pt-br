---
title: Caixa de diálogo de Ferramentas Externas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- adding external tools
- external tools [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], external tools
ms.assetid: ba797203-24d0-4922-9b97-8ab483f1db14
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5789dc150e45c1a0364b7acc0ea7fda443efcf17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681360"
---
# <a name="external-tools-dialog-box"></a><span data-ttu-id="842e9-102">Caixa de diálogo Ferramentas Externas</span><span class="sxs-lookup"><span data-stu-id="842e9-102">External Tools Dialog Box</span></span>
  <span data-ttu-id="842e9-103">Use a caixa de diálogo **Ferramentas Externas** para adicionar ferramentas externas como SQLCMD ou o Bloco de Notas ao menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="842e9-103">Use the **External Tools** dialog box to add external tools such as SQLCMD or Notepad to the **Tools** menu.</span></span> <span data-ttu-id="842e9-104">Adicionar ferramentas externas permite a inicialização de outros aplicativos facilmente enquanto você trabalha no ambiente do [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="842e9-104">Adding external tools allows you to easily launch other applications while working in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span> <span data-ttu-id="842e9-105">Você pode especificar argumentos e um diretório de trabalho na execução da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="842e9-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="842e9-106">Além disso, a saída de algumas ferramentas pode ser exibida na janela **Saída** .</span><span class="sxs-lookup"><span data-stu-id="842e9-106">In addition, the output from some tools can be displayed in the **Output** window.</span></span> <span data-ttu-id="842e9-107">A caixa de diálogo **Ferramentas Externas** está disponível no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="842e9-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="842e9-108">Opções</span><span class="sxs-lookup"><span data-stu-id="842e9-108">Options</span></span>  
 <span data-ttu-id="842e9-109">**Conteúdos de menu**</span><span class="sxs-lookup"><span data-stu-id="842e9-109">**Menu contents**</span></span>  
 <span data-ttu-id="842e9-110">Relaciona os títulos dos itens atuais adicionados ao menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="842e9-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="842e9-111">Use as setas **Mover para Cima** e **Mover para Baixo** para alterar a ordem dos itens que aparecem no menu.</span><span class="sxs-lookup"><span data-stu-id="842e9-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="842e9-112">Use o botão **Excluir** para remover um item do menu.</span><span class="sxs-lookup"><span data-stu-id="842e9-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="842e9-113">**Mover para Cima**</span><span class="sxs-lookup"><span data-stu-id="842e9-113">**Move Up**</span></span>  
 <span data-ttu-id="842e9-114">Mova a ferramenta selecionada para cima na lista de ferramentas exibida no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="842e9-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="842e9-115">**Mover para Baixo**</span><span class="sxs-lookup"><span data-stu-id="842e9-115">**Move Down**</span></span>  
 <span data-ttu-id="842e9-116">Mova a ferramenta selecionada para baixo na lista de ferramentas exibida no menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="842e9-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="842e9-117">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="842e9-117">**Add**</span></span>  
 <span data-ttu-id="842e9-118">Desmarque as caixas de texto para que você possa especificar uma nova ferramenta.</span><span class="sxs-lookup"><span data-stu-id="842e9-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="842e9-119">**Delete (excluir)**</span><span class="sxs-lookup"><span data-stu-id="842e9-119">**Delete**</span></span>  
 <span data-ttu-id="842e9-120">Remova a ferramenta ou o comando da lista **Conteúdo do Menu** , bem como do menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="842e9-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="842e9-121">**Título**</span><span class="sxs-lookup"><span data-stu-id="842e9-121">**Title**</span></span>  
 <span data-ttu-id="842e9-122">Insira o nome da ferramenta ou do comando que será exibido no submenu **Ferramentas Externas** do menu **Ferramentas** .</span><span class="sxs-lookup"><span data-stu-id="842e9-122">Enter the name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="842e9-123">Coloque um E comercial (&) antes de uma letra no nome da ferramenta para especificar essa letra como uma tecla de atalho.</span><span class="sxs-lookup"><span data-stu-id="842e9-123">Place an ampersand (&) before a letter in the name of the tool to specify that letter as a keyboard shortcut.</span></span> <span data-ttu-id="842e9-124">Por exemplo, "&SQLCMD" mostrará SQLCMD no menu **Ferramentas**.</span><span class="sxs-lookup"><span data-stu-id="842e9-124">For example, "&SQLCMD" would display SQLCMD on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="842e9-125">**Comando**</span><span class="sxs-lookup"><span data-stu-id="842e9-125">**Command**</span></span>  
 <span data-ttu-id="842e9-126">Especifique o caminho do arquivo a ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="842e9-126">Specify the path to the file to launch.</span></span>  
  
 <span data-ttu-id="842e9-127">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="842e9-127">**Arguments**</span></span>  
 <span data-ttu-id="842e9-128">Especifique as variáveis que serão passadas à ferramenta quando a ferramenta for selecionada no menu.</span><span class="sxs-lookup"><span data-stu-id="842e9-128">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="842e9-129">Os argumentos podem especificar valores que são passados à ferramenta ou ao comando quando são iniciados.</span><span class="sxs-lookup"><span data-stu-id="842e9-129">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="842e9-130">Por exemplo, um valor pode especificar um nome de arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="842e9-130">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="842e9-131">Use o botão de seta para fazer a seleção em uma lista de argumentos predefinidos.</span><span class="sxs-lookup"><span data-stu-id="842e9-131">Use the arrow button to select from a list of predefined arguments.</span></span> <span data-ttu-id="842e9-132">Você pode adicionar mais de um argumento.</span><span class="sxs-lookup"><span data-stu-id="842e9-132">You can add more than one.</span></span> <span data-ttu-id="842e9-133">Para obter uma lista completa de argumentos predefinidos e suas definições, consulte [Arguments for External Tools](menu-help/external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="842e9-133">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](menu-help/external-tools.md).</span></span> <span data-ttu-id="842e9-134">Você também pode inserir argumentos personalizados (por exemplo, opções de linha de comando), dependendo do comando ou da ferramenta usada.</span><span class="sxs-lookup"><span data-stu-id="842e9-134">You can also enter custom arguments (for example, command line switches), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="842e9-135">**Usar a janela Saída**</span><span class="sxs-lookup"><span data-stu-id="842e9-135">**Use Output window**</span></span>  
 <span data-ttu-id="842e9-136">Abre a janela Saída do [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] para exibir a saída do comando que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="842e9-136">Opens the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Output window to display output of the command being run.</span></span> <span data-ttu-id="842e9-137">Nem todas as ferramentas apresentam saída em um formato que pode ser exibido na janela Saída.</span><span class="sxs-lookup"><span data-stu-id="842e9-137">Not all tools present output in a format that can be presented in the Output window.</span></span> <span data-ttu-id="842e9-138">Para obter mais informações, consulte [Janela Saída](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span><span class="sxs-lookup"><span data-stu-id="842e9-138">For more information, see [Output Window](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span></span>  
  
 <span data-ttu-id="842e9-139">**Tratar saída como Unicode**</span><span class="sxs-lookup"><span data-stu-id="842e9-139">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="842e9-140">Interpreta a saída como Unicode.</span><span class="sxs-lookup"><span data-stu-id="842e9-140">Interprets the output as Unicode.</span></span>  
  
 <span data-ttu-id="842e9-141">**Diretório inicial**</span><span class="sxs-lookup"><span data-stu-id="842e9-141">**Initial directory**</span></span>  
 <span data-ttu-id="842e9-142">Especifique o diretório de trabalho da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="842e9-142">Specify the working directory of the tool.</span></span> <span data-ttu-id="842e9-143">Use o botão de seta para selecionar diretórios.</span><span class="sxs-lookup"><span data-stu-id="842e9-143">Use the arrow button to select directories.</span></span> <span data-ttu-id="842e9-144">Você pode selecionar mais de um argumento.</span><span class="sxs-lookup"><span data-stu-id="842e9-144">You can select more than one.</span></span>  
  
 <span data-ttu-id="842e9-145">**Solicitar argumentos**</span><span class="sxs-lookup"><span data-stu-id="842e9-145">**Prompt for arguments**</span></span>  
 <span data-ttu-id="842e9-146">Exibe a caixa de diálogo **Argumentos** para permitir a inserção ou edição dos valores para os argumentos sempre que você iniciar a ferramenta externa.</span><span class="sxs-lookup"><span data-stu-id="842e9-146">Display the **Arguments** dialog box to allow you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="842e9-147">**Fechar na saída**</span><span class="sxs-lookup"><span data-stu-id="842e9-147">**Close on exit**</span></span>  
 <span data-ttu-id="842e9-148">Fecha a janela aberta pela ferramenta quando ela for encerrada.</span><span class="sxs-lookup"><span data-stu-id="842e9-148">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="842e9-149">Exemplo</span><span class="sxs-lookup"><span data-stu-id="842e9-149">Example</span></span>  
 <span data-ttu-id="842e9-150">Inserir os valores a seguir na caixa de diálogo **Ferramentas Externas** criará um item de menu rotulado como "DAC" que, quando selecionado, abrirá um prompt de comando e executará o utilitário **sqlcmd** usando a conexão de administrador dedicada.</span><span class="sxs-lookup"><span data-stu-id="842e9-150">Entering the following values in the **External Tools** dialog box will create a menu item labeled "DAC" that when selected, opens a command prompt and runs the **sqlcmd** utility using the dedicated administrator connection.</span></span>  
  
|<span data-ttu-id="842e9-151">Box</span><span class="sxs-lookup"><span data-stu-id="842e9-151">Box</span></span>|<span data-ttu-id="842e9-152">Valor</span><span class="sxs-lookup"><span data-stu-id="842e9-152">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="842e9-153">**Título**</span><span class="sxs-lookup"><span data-stu-id="842e9-153">**Title**</span></span>|<span data-ttu-id="842e9-154">DAC</span><span class="sxs-lookup"><span data-stu-id="842e9-154">DAC</span></span>|  
|<span data-ttu-id="842e9-155">**Comando**</span><span class="sxs-lookup"><span data-stu-id="842e9-155">**Command**</span></span>|[!INCLUDE[ssInstallPath](../includes/ssinstallpath-md.md)]<span data-ttu-id="842e9-156">Tools\Binn\SQLCMD.exe</span><span class="sxs-lookup"><span data-stu-id="842e9-156">Tools\Binn\SQLCMD.exe</span></span>|  
|<span data-ttu-id="842e9-157">**Argumentos**</span><span class="sxs-lookup"><span data-stu-id="842e9-157">**Arguments**</span></span>|<span data-ttu-id="842e9-158">-A</span><span class="sxs-lookup"><span data-stu-id="842e9-158">-A</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="842e9-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="842e9-159">See Also</span></span>  
 <span data-ttu-id="842e9-160">[Argumentos para ferramentas externas](menu-help/external-tools.md) </span><span class="sxs-lookup"><span data-stu-id="842e9-160">[Arguments for External Tools](menu-help/external-tools.md) </span></span>  
 [<span data-ttu-id="842e9-161">Elementos gerais da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="842e9-161">General User Interface Elements</span></span>](general-user-interface-elements.md)  
  
  
