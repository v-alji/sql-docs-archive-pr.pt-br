---
title: 'Tarefa 15: Compilando e executando o projeto do SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13adf4e0-216a-4992-b13d-b7b1e1629e77
ms.author: lle
author: lrtoyou1223
ms.openlocfilehash: 2a008cd848c95b48e6e22798b6ef903942b4d656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681945"
---
# <a name="task-15-building-and-running-the-ssis-project"></a><span data-ttu-id="88338-102">Tarefa 15: Criando e executando o projeto SSIS</span><span class="sxs-lookup"><span data-stu-id="88338-102">Task 15: Building and Running the SSIS Project</span></span>

  <span data-ttu-id="88338-103">Nesta tarefa, você criará e executará o projeto SSIS.</span><span class="sxs-lookup"><span data-stu-id="88338-103">In this task, you build and run the SSIS project.</span></span> <span data-ttu-id="88338-104">Se você tiver a versão de 64 bits do Excel 2010 instalada em seu computador, defina o valor de **Run64BitRuntime** como **false** para que a origem do Excel funcione.</span><span class="sxs-lookup"><span data-stu-id="88338-104">If you have the 64-bit version of Excel 2010 installed on your computer, you should set the value of **Run64BitRuntime** to **False** for the Excel source to work.</span></span>  
  
1.  <span data-ttu-id="88338-105">Na janela **Gerenciador de soluções** , clique em **projeto** no menu e clique em **Propriedades de CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="88338-105">In the **Solution Explorer** window, click **Project** on the menu, and click **CleanseAndCurateSuppliers Properties**.</span></span>  
  
2.  <span data-ttu-id="88338-106">Na caixa de diálogo **Propriedades** , expanda **Propriedades de configuração** à esquerda e clique em **depuração**.</span><span class="sxs-lookup"><span data-stu-id="88338-106">In the **Properties** dialog box, expand **Configuration Properties** on left, and click **Debugging**.</span></span>  
  
3.  <span data-ttu-id="88338-107">Defina **Run64BitRuntime** como **false**.</span><span class="sxs-lookup"><span data-stu-id="88338-107">Set **Run64BitRuntime** to **False**.</span></span>  
  
     <span data-ttu-id="88338-108">![Propriedades do Projeto CleanseAndCurateSuppliers](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "Propriedades do Projeto CleanseAndCurateSuppliers")</span><span class="sxs-lookup"><span data-stu-id="88338-108">![CleanseAndCurateSuppliers Project Properties](../../2014/tutorials/media/et-buildingandrunningthessisproject-01.jpg "CleanseAndCurateSuppliers Project Properties")</span></span>  
  
4.  <span data-ttu-id="88338-109">Clique em **OK** para fechar a caixa de diálogo **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="88338-109">Click **OK** to close the **Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="88338-110">Clique em **criar** na barra de menus e clique em **criar CleanseAndCurateSuppliers**.</span><span class="sxs-lookup"><span data-stu-id="88338-110">Click **Build** on menu bar and click **Build CleanseAndCurateSuppliers**.</span></span> <span data-ttu-id="88338-111">Verifique se não há erros de compilação.</span><span class="sxs-lookup"><span data-stu-id="88338-111">Make sure that there are no build errors.</span></span>  
  
6.  <span data-ttu-id="88338-112">Clique em **depurar** na barra de menus e clique em **Iniciar Depuração**.</span><span class="sxs-lookup"><span data-stu-id="88338-112">Click **Debug** on the menu bar and click **Start Debugging**.</span></span>  
  
7.  <span data-ttu-id="88338-113">Examine as mensagens na janela de **progresso** e verifique se o pacote foi executado e foi concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="88338-113">Review messages in the **Progress** window and verify that package executed and ended successfully.</span></span>  
  
     <span data-ttu-id="88338-114">![Resultados da janela de progresso](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Resultados da janela de progresso")</span><span class="sxs-lookup"><span data-stu-id="88338-114">![Results from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-02.jpg "Results from Progress Window")</span></span>  
  
     <span data-ttu-id="88338-115">![Status final da janela de progresso](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Status final da janela de progresso")</span><span class="sxs-lookup"><span data-stu-id="88338-115">![Final Status from Progress Window](../../2014/tutorials/media/et-buildingandrunningthessisproject-03.jpg "Final Status from Progress Window")</span></span>  
  
8.  <span data-ttu-id="88338-116">Clique em **depurar** na barra de menus e clique em **parar depuração** para interromper a sessão de depuração.</span><span class="sxs-lookup"><span data-stu-id="88338-116">Click **Debug** on menu bar and click **Stop Debugging** to stop the debugging session.</span></span> <span data-ttu-id="88338-117">Se o pacote falhar, você deverá habilitar visualizadores de dados e verificar como os dados fluem entre os componentes.</span><span class="sxs-lookup"><span data-stu-id="88338-117">If the package fails, you should enable data viewers and see how the data flows between components.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="88338-118">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="88338-118">Next Step</span></span>  
 [<span data-ttu-id="88338-119">Tarefa 16: Verificando com o Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="88338-119">Task 16: Verifying with Master Data Manager</span></span>](../../2014/tutorials/task-16-verifying-with-master-data-manager.md)  
  
  
