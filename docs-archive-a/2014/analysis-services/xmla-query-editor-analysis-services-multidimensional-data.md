---
title: Editor de Consultas XMLA (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.editor.xmla.f1
helpviewer_keywords:
- XMLA Query Editor
- Query Editor [XMLA]
ms.assetid: 14623019-7839-4038-9d12-2f8953d2ec04
author: minewiskan
ms.author: owend
ms.openlocfilehash: a36dcbd49b4f24c34a07abdfb10509ff1eb52a0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570283"
---
# <a name="xmla-query-editor-analysis-services---multidimensional-data"></a><span data-ttu-id="f41a1-102">Editor de Consultas XMLA (Analysis Services – Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="f41a1-102">XMLA Query Editor (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="f41a1-103">Use o Editor de Consultas XMLA para criar e executar instruções e scripts escritos na linguagem XMLA (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="f41a1-103">Use the XMLA Query Editor to design and execute statements and scripts written in the Multidimensional Expressions (XMLA) language.</span></span>  
  
## <a name="features"></a><span data-ttu-id="f41a1-104">Recursos</span><span class="sxs-lookup"><span data-stu-id="f41a1-104">Features</span></span>  
  
-   <span data-ttu-id="f41a1-105">Digite os scripts no painel do Editor de Consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="f41a1-105">Type scripts in the query editor pane of XMLA Query Editor.</span></span>  
  
-   <span data-ttu-id="f41a1-106">Para executar scripts, pressione **F5**ou clique em **Executar** na barra de ferramentas ou, no menu **Consulta** , clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f41a1-106">To execute scripts press **F5**, or click **Execute** on the toolbar, or on the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="f41a1-107">Se uma parte do código estiver selecionada, só essa parte será executada.</span><span class="sxs-lookup"><span data-stu-id="f41a1-107">If a portion of the code is selected, only that portion is executed.</span></span> <span data-ttu-id="f41a1-108">Se nenhum código for selecionado, todo o conteúdo do Editor de Consultas XMLA será executado.</span><span class="sxs-lookup"><span data-stu-id="f41a1-108">If no code is selected, the entire content of the XMLA Query Editor is executed.</span></span>  
  
-   <span data-ttu-id="f41a1-109">Exiba metadados para cubos e outros objetos contidos em um banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] no painel de metadados.</span><span class="sxs-lookup"><span data-stu-id="f41a1-109">View metadata for cubes and other objects contained in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database in the metadata pane.</span></span>  
  
-   <span data-ttu-id="f41a1-110">Para obter ajuda sobre a sintaxe XMLA, selecione uma palavra-chave no Editor de Consultas XMLA e clique em **F1**.</span><span class="sxs-lookup"><span data-stu-id="f41a1-110">For help with XMLA syntax, select a keyword in XMLA Query Editor, and then click **F1**.</span></span>  
  
-   <span data-ttu-id="f41a1-111">Para obter ajuda dinâmica sobre a sintaxe XMLA, no menu **Ajuda** , clique em **Ajuda Dinâmica** para abrir o componente da Ajuda Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="f41a1-111">For dynamic help with XMLA syntax, on the **Help** menu, click **Dynamic Help** to open the Dynamic Help component.</span></span> <span data-ttu-id="f41a1-112">Com a Ajuda Dinâmica, os tópicos de ajuda aparecem na janela **Ajuda Dinâmica** quando são digitadas palavras-chave no Editor de Consultas.</span><span class="sxs-lookup"><span data-stu-id="f41a1-112">With Dynamic Help, help topics appear in the **Dynamic Help** window when keywords are typed in Query Editor.</span></span>  
  
## <a name="sql-server-analysis-services-editors-toolbar"></a><span data-ttu-id="f41a1-113">Barra de ferramentas de Editores do SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="f41a1-113">SQL Server Analysis Services Editors Toolbar</span></span>  
 <span data-ttu-id="f41a1-114">Quando o Editor de Consultas XMLA está aberto, a barra de ferramentas dos **Editores do SQL Server Analysis Services** é exibida com os botões a seguir.</span><span class="sxs-lookup"><span data-stu-id="f41a1-114">When XMLA Query Editor is open, the **SQL Server Analysis Services Editors** toolbar appears with the following buttons.</span></span>  
  
|<span data-ttu-id="f41a1-115">Termo</span><span class="sxs-lookup"><span data-stu-id="f41a1-115">Term</span></span>|<span data-ttu-id="f41a1-116">Definição</span><span class="sxs-lookup"><span data-stu-id="f41a1-116">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="f41a1-117">**Connect**</span><span class="sxs-lookup"><span data-stu-id="f41a1-117">**Connect**</span></span>|<span data-ttu-id="f41a1-118">Abre a caixa de diálogo **Conectar ao Servidor** para estabelecer uma conexão com uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f41a1-118">Opens the **Connect to Server** dialog box, to establish a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>|  
|<span data-ttu-id="f41a1-119">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="f41a1-119">**Disconnect**</span></span>|<span data-ttu-id="f41a1-120">Desconecta o Editor de Consultas XMLA de uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f41a1-120">Disconnects the XMLA Query Editor from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>|  
|<span data-ttu-id="f41a1-121">**Alterar Conexão**</span><span class="sxs-lookup"><span data-stu-id="f41a1-121">**Change Connection**</span></span>|<span data-ttu-id="f41a1-122">Abre a caixa de diálogo **Conectar ao Servidor** para estabelecer uma conexão com uma instância diferente do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f41a1-122">Opens the **Connect to Server** dialog box, to establish a connection to a different [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>|  
|<span data-ttu-id="f41a1-123">**Nova Consulta com Conexão Atual**</span><span class="sxs-lookup"><span data-stu-id="f41a1-123">**New Query with Current Connection**</span></span>|<span data-ttu-id="f41a1-124">Abre uma nova janela do Editor de Consultas XMLA, utilizando as informações de conexão da janela atual do Editor de Consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="f41a1-124">Opens a new XMLA Query Editor window, using the connection information from the current XMLA Query Editor window.</span></span>|  
|<span data-ttu-id="f41a1-125">**Bancos de Dados Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="f41a1-125">**Available Databases**</span></span>|<span data-ttu-id="f41a1-126">Altera a conexão para outro banco de dados do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] na mesma instância.</span><span class="sxs-lookup"><span data-stu-id="f41a1-126">Changes the connection to a different [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database on the same instance.</span></span>|  
|<span data-ttu-id="f41a1-127">**Executados**</span><span class="sxs-lookup"><span data-stu-id="f41a1-127">**Execute**</span></span>|<span data-ttu-id="f41a1-128">Executa o código selecionado ou, se nenhum código for selecionado, esta opção executará todo o código no Editor de Consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="f41a1-128">Executes the selected code, or if no code is selected, this option executes the entire code in the XMLA Query Editor.</span></span>|  
|<span data-ttu-id="f41a1-129">**Analisar**</span><span class="sxs-lookup"><span data-stu-id="f41a1-129">**Parse**</span></span>|<span data-ttu-id="f41a1-130">Verifica a sintaxe do código selecionado.</span><span class="sxs-lookup"><span data-stu-id="f41a1-130">Checks the syntax of the selected code.</span></span> <span data-ttu-id="f41a1-131">Se nenhum código for selecionado, essa opção verificará a sintaxe de toda a janela Editor de Consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="f41a1-131">If no code is selected, this option checks the syntax of the entire XMLA Query Editor window.</span></span>|  
|<span data-ttu-id="f41a1-132">**Cancelar Consulta de Execução**</span><span class="sxs-lookup"><span data-stu-id="f41a1-132">**Cancel Executing Query**</span></span>|<span data-ttu-id="f41a1-133">Envia uma solicitação de cancelamento ao servidor.</span><span class="sxs-lookup"><span data-stu-id="f41a1-133">Sends a cancellation request to the server.</span></span> <span data-ttu-id="f41a1-134">Algumas consultas não podem ser canceladas imediatamente, mas precisam esperar por uma condição de cancelamento satisfatória.</span><span class="sxs-lookup"><span data-stu-id="f41a1-134">Some queries cannot be canceled immediately, but must wait for a suitable cancellation condition.</span></span> <span data-ttu-id="f41a1-135">Quando consultas são canceladas, podem ocorrer atrasos enquanto as transações são convertidas.</span><span class="sxs-lookup"><span data-stu-id="f41a1-135">When queries are canceled, delays may occur while transactions are rolled back.</span></span>|  
  
## <a name="xmla-query-editor-window"></a><span data-ttu-id="f41a1-136">Janela Editor de Consultas XMLA</span><span class="sxs-lookup"><span data-stu-id="f41a1-136">XMLA Query Editor Window</span></span>  
 <span data-ttu-id="f41a1-137">As seguintes opções estão disponíveis no Editor de Consultas XMLA:</span><span class="sxs-lookup"><span data-stu-id="f41a1-137">The following options are available in XMLA Query Editor:</span></span>  
  
|<span data-ttu-id="f41a1-138">Termo</span><span class="sxs-lookup"><span data-stu-id="f41a1-138">Term</span></span>|<span data-ttu-id="f41a1-139">Definição</span><span class="sxs-lookup"><span data-stu-id="f41a1-139">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="f41a1-140">**janela Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="f41a1-140">**Query editor window**</span></span>|<span data-ttu-id="f41a1-141">Digite as instruções e os scripts XMLA a serem executados pelo Editor de Consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="f41a1-141">Type XMLA statements and scripts to be executed by the XMLA Query Editor.</span></span><br /><br /> <span data-ttu-id="f41a1-142">O menu de contexto do editor de consultas fornece as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f41a1-142">The context menu for the query editor provides the following options:</span></span><br /><br /> <span data-ttu-id="f41a1-143">**Recortar**: copia a seleção atual para a área de transferência e remove a seleção da janela do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="f41a1-143">**Cut**: Copies the current selection to the clipboard and removes the selection from the query editor window.</span></span><br /><span data-ttu-id="f41a1-144">**Copiar**: copia a seleção atual para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="f41a1-144">**Copy**: Copies the current selection to the clipboard.</span></span><br /><span data-ttu-id="f41a1-145">**Colar**: cola o conteúdo da área de transferência na seleção atual.</span><span class="sxs-lookup"><span data-stu-id="f41a1-145">**Paste**: Pastes the contents of the clipboard to the current selection.</span></span><br /><span data-ttu-id="f41a1-146">**Conectar**: abre a caixa de diálogo **Conectar ao Servidor** para estabelecer uma conexão com uma instância do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f41a1-146">**Connect**: Opens the **Connect to Server** dialog box, to establish a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span><br /><span data-ttu-id="f41a1-147">**Desconectar: desconecta**o editor de consultas atual de uma [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instância.</span><span class="sxs-lookup"><span data-stu-id="f41a1-147">**Disconnect**: Disconnects the current query editor from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span><br /><span data-ttu-id="f41a1-148">**Desconectar todas as consultas: desconecta**todos os editores de consulta abertos.</span><span class="sxs-lookup"><span data-stu-id="f41a1-148">**Disconnect All Queries**: Disconnects all open query editors.</span></span><br /><span data-ttu-id="f41a1-149">**Alterar conexão**: abre a caixa de diálogo **conectar ao servidor** para estabelecer uma conexão com uma [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instância diferente.</span><span class="sxs-lookup"><span data-stu-id="f41a1-149">**Change Connection**: Opens the **Connect to Server** dialog box, to establish a connection to a different [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span><br /><span data-ttu-id="f41a1-150">**Abrir servidor no Pesquisador de objetos**: abre a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instância para a qual o editor de consultas atual está conectado no **pesquisador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="f41a1-150">**Open Server in Object Explorer**: Opens the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to which the current query editor is connected in **Object Explorer**.</span></span><br /><span data-ttu-id="f41a1-151">**Execute**: executa o código selecionado ou, se nenhum código for selecionado, executa todo o código no editor de consultas atual.</span><span class="sxs-lookup"><span data-stu-id="f41a1-151">**Execute**: Executes the selected code, or if no code is selected, executes the entire code in the current query editor.</span></span><br /><span data-ttu-id="f41a1-152">**Janela Propriedades**: exibe a janela **Propriedades** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para a janela de consulta atual.</span><span class="sxs-lookup"><span data-stu-id="f41a1-152">**Properties Window**: Displays the **Properties** window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for the current query window.</span></span><br /><span data-ttu-id="f41a1-153">**Opções de consulta**: exibe a caixa de diálogo **Opções de consulta** .</span><span class="sxs-lookup"><span data-stu-id="f41a1-153">**Query Options**: Displays the **Query Options** dialog box.</span></span>|  
|<span data-ttu-id="f41a1-154">**Janela Resultados**</span><span class="sxs-lookup"><span data-stu-id="f41a1-154">**Results window**</span></span>|<span data-ttu-id="f41a1-155">Exibe os resultados de uma instrução ou script XMLA em texto.</span><span class="sxs-lookup"><span data-stu-id="f41a1-155">Displays the results of an XMLA statement or script in text.</span></span>|  
|<span data-ttu-id="f41a1-156">**Janela Mensagens**</span><span class="sxs-lookup"><span data-stu-id="f41a1-156">**Messages window**</span></span>|<span data-ttu-id="f41a1-157">Exibe informações sobre como uma instrução ou script XMLA foi executado.</span><span class="sxs-lookup"><span data-stu-id="f41a1-157">Displays information about how an XMLA statement or script executed.</span></span> <span data-ttu-id="f41a1-158">Por exemplo, esta janela exibe todos os erros encontrados durante a execução ou o número de células recuperados depois da execução.</span><span class="sxs-lookup"><span data-stu-id="f41a1-158">For example, this window displays any errors encountered during execution or the number of cells retrieved after execution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f41a1-159">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f41a1-159">See Also</span></span>  
 <span data-ttu-id="f41a1-160">[Editor de consultas MDX &#40;Analysis Services de dados multidimensionais&#41;](mdx-query-editor-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f41a1-160">[MDX Query Editor &#40;Analysis Services - Multidimensional Data&#41;](mdx-query-editor-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="f41a1-161">[Editor de consultas DMX &#40;Analysis Services de mineração de dados&#41;](dmx-query-editor-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="f41a1-161">[DMX Query Editor &#40;Analysis Services - Data Mining&#41;](dmx-query-editor-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="f41a1-162">[Editores de consulta e de texto &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="f41a1-162">[Query and Text Editors &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="f41a1-163">Atalhos de teclado do SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f41a1-163">SQL Server Management Studio Keyboard Shortcuts</span></span>](../ssms/sql-server-management-studio-keyboard-shortcuts.md)  
  
  