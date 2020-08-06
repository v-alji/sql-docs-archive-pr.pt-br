---
title: 'Etapa 3: modificar o gerenciador de conexões de arquivo simples | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 459e3995-2116-4f15-aaa2-32f26113869c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b897f9412a8f2978ebe4137e3e79bf1d28c97844
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570118"
---
# <a name="step-3-modifying-the-flat-file-connection-manager"></a><span data-ttu-id="5df07-102">Etapa 3: Modificar o gerenciador de conexões de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="5df07-102">Step 3: Modifying the Flat File Connection Manager</span></span>
  <span data-ttu-id="5df07-103">Nesta tarefa, você modificará o gerenciador de conexões de arquivo simples que você criou e configurou na Lição 1.</span><span class="sxs-lookup"><span data-stu-id="5df07-103">In this task, you will modify the Flat File connection manager that you created and configured in Lesson 1.</span></span> <span data-ttu-id="5df07-104">Quando foi criado originalmente, o gerenciador de conexões de arquivo simples foi configurado para carregar estatisticamente um único arquivo.</span><span class="sxs-lookup"><span data-stu-id="5df07-104">When originally created, the Flat File connection manager was configured to statically load a single file.</span></span> <span data-ttu-id="5df07-105">Para habilitar o gerenciador de conexões de Arquivo Simples a carregar arquivos de forma iterativa, você deve modificar a propriedade ConnectionString do gerenciador de conexões para aceitar a variável definida pelo usuário `User:varFileName`, que contém o caminho do arquivo a ser carregado em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="5df07-105">To enable the Flat File connection manager to iteratively load files, you must modify the ConnectionString property of the connection manager to accept the user-defined variable `User:varFileName`, which contains the path of the file to be loaded at run time.</span></span>  
  
 <span data-ttu-id="5df07-106">Ao modificar o gerenciador de conexões para usar o valor da variável definida pelo usuário, `User::varFileName`, para popular a propriedade ConnectionString do gerenciador de conexões, o gerenciador de conexões poderá se conectar a diferentes arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="5df07-106">By modifying the connection manager to use the value of the user-defined variable, `User::varFileName`, to populate the ConnectionString property of the connection manager, the connection manager will be able to connect to different flat files.</span></span> <span data-ttu-id="5df07-107">No tempo de execução, cada iteração do contêiner Loop Foreach atualizará dinamicamente a variável `User::varFileName` .</span><span class="sxs-lookup"><span data-stu-id="5df07-107">At run time, each iteration of the Foreach Loop container will dynamically update the `User::varFileName` variable.</span></span> <span data-ttu-id="5df07-108">Atualizar a variável, por sua vez, faz com que o gerenciador de conexões se conecte a um arquivo simples diferente e a tarefa de fluxo de dados processe um conjunto diferente de dados.</span><span class="sxs-lookup"><span data-stu-id="5df07-108">Updating the variable, in turn, causes the connection manager to connect to a different flat file, and the data flow task to process a different set of data.</span></span>  
  
### <a name="to-configure-the-flat-file-connection-manager-to-use-a-variable-for-the-connection-string"></a><span data-ttu-id="5df07-109">Para configurar o gerenciador de conexões de arquivo simples para usar uma variável para a cadeia de conexão</span><span class="sxs-lookup"><span data-stu-id="5df07-109">To configure the Flat File connection manager to use a variable for the connection string</span></span>  
  
1.  <span data-ttu-id="5df07-110">No painel **Gerenciadores de Conexões** , clique com o botão direito do mouse em **Dados de Origem de Arquivo Simples de Exemplo**e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5df07-110">In the **Connection Managers** pane, right-click **Sample Flat File Source Data**, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5df07-111">No janela Propriedades, para **expressões**, clique na célula vazia e, em seguida, clique no botão de reticências **(...)**.</span><span class="sxs-lookup"><span data-stu-id="5df07-111">In the Properties window, for **Expressions**, click in the empty cell, and then click the ellipsis button **(...)**.</span></span>  
  
3.  <span data-ttu-id="5df07-112">Na caixa de diálogo **Editor de expressões de propriedade** , na coluna **Propriedade** , digite ou selecione `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="5df07-112">In the **Property Expressions Editor** dialog box, in the **Property** column, type or select `ConnectionString`.</span></span>  
  
4.  <span data-ttu-id="5df07-113">Na coluna **expressão** , clique no botão de reticências **(...)** para abrir a caixa de diálogo **Construtor de expressões** .</span><span class="sxs-lookup"><span data-stu-id="5df07-113">In the **Expression** column, click the ellipsis button **(...)** to open the **Expression Builder** dialog box.</span></span>  
  
5.  <span data-ttu-id="5df07-114">Na caixa de diálogo **Construtor de Expressão** , expanda o nó **Variáveis** .</span><span class="sxs-lookup"><span data-stu-id="5df07-114">In the **Expression Builder** dialog box, expand the **Variables** node.</span></span>  
  
6.  <span data-ttu-id="5df07-115">Arraste a variável, **User:: varFileName**, para a caixa **expressão** .</span><span class="sxs-lookup"><span data-stu-id="5df07-115">Drag the variable, **User::varFileName**, into the **Expression** box.</span></span>  
  
7.  <span data-ttu-id="5df07-116">Clique em **OK** para fechar a caixa de diálogo **Construtor de Expressão** .</span><span class="sxs-lookup"><span data-stu-id="5df07-116">Click **OK** to close the **Expression Builder** dialog box.</span></span>  
  
8.  <span data-ttu-id="5df07-117">Clique em **OK** novamente para fechar a caixa de diálogo **Editor de Expressões de Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="5df07-117">Click **OK** again to close the **Property Expressions Editor** dialog box.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="5df07-118">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="5df07-118">Next Lesson Task</span></span>  
 [<span data-ttu-id="5df07-119">Etapa 4: Testar o pacote de tutorial da Lição 2</span><span class="sxs-lookup"><span data-stu-id="5df07-119">Step 4: Testing the Lesson 2 Tutorial Package</span></span>](../integration-services/lesson-2-4-testing-the-lesson-2-tutorial-package.md)  
  
  
