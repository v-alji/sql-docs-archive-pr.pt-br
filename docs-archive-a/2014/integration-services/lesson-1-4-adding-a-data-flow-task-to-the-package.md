---
title: 'Etapa 4: adicionar uma tarefa de fluxo de dados ao pacote | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 96af3073-8f11-4444-b934-fe8613a2d084
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4fda1de99e9fcaa683f9063e2feb1b71886a5cd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574137"
---
# <a name="step-4-adding-a-data-flow-task-to-the-package"></a><span data-ttu-id="79b0f-102">Etapa 4: Adicionar uma tarefa de fluxo de dados ao pacote</span><span class="sxs-lookup"><span data-stu-id="79b0f-102">Step 4: Adding a Data Flow Task to the Package</span></span>
  <span data-ttu-id="79b0f-103">Depois de criar os gerenciadores de conexões para os dados de origem e destino, a próxima tarefa é adicionar a tarefa Fluxo de Dados ao seu pacote.</span><span class="sxs-lookup"><span data-stu-id="79b0f-103">After you have created the connection managers for the source and destination data, the next task is to add a Data Flow task to your package.</span></span> <span data-ttu-id="79b0f-104">Essa tarefa encapsula o mecanismo de fluxo de dados que move dados entre as origens e os destinos, além de fornecer funcionalidade para transformar, limpar e modificar os dados à medida que são movidos.</span><span class="sxs-lookup"><span data-stu-id="79b0f-104">The Data Flow task encapsulates the data flow engine that moves data between sources and destinations, and provides the functionality for transforming, cleaning, and modifying data as it is moved.</span></span> <span data-ttu-id="79b0f-105">A tarefa Fluxo de Dados é onde a maioria do trabalho de um processo de extração, transformação e carregamento (ETL) acontece.</span><span class="sxs-lookup"><span data-stu-id="79b0f-105">The Data Flow task is where most of the work of an extract, transform, and load (ETL) process occurs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="79b0f-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]separa o fluxo de dados do fluxo de controle.</span><span class="sxs-lookup"><span data-stu-id="79b0f-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates data flow from control flow.</span></span>  
  
### <a name="to-add-a-data-flow-task"></a><span data-ttu-id="79b0f-107">Adicionar uma tarefa Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="79b0f-107">To add a Data Flow task</span></span>  
  
1.  <span data-ttu-id="79b0f-108">Clique na guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="79b0f-108">Click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="79b0f-109">Na **Caixa de Ferramentas do SSIS**, expanda **Favoritos**e arraste uma **Tarefa de Fluxo de Dados** até a superfície de design da guia **Fluxo de Controle** .</span><span class="sxs-lookup"><span data-stu-id="79b0f-109">In the **SSIS Toolbox**, expand **Favorites**, and drag a **Data Flow Task** onto the design surfaceof the **Control Flow** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79b0f-110">Se a Caixa de Ferramentas do SSIS não estiver disponível, no menu principal, selecione Caixa de Ferramentas do SSIS para exibir a Caixa de Ferramentas do SSIS.</span><span class="sxs-lookup"><span data-stu-id="79b0f-110">If the SSIS Toolbox isn't available, on the main menu select SSIS then SSIS Toolbox to display the SSIS Toolbox.</span></span>  
  
3.  <span data-ttu-id="79b0f-111">Na superfície de design do **fluxo de controle** , clique com o botão direito do mouse na tarefa de **fluxo de dados**recém adicionada, clique em **renomear**e altere o nome para `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="79b0f-111">On the **Control Flow** design surface, right-click the newly added **Data Flow Task**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
     <span data-ttu-id="79b0f-112">É uma boa ideia fornecer nomes exclusivos a todos os componentes que você adiciona a uma superfície de design.</span><span class="sxs-lookup"><span data-stu-id="79b0f-112">It is good practice to provide unique names to all components that you add to a design surface.</span></span> <span data-ttu-id="79b0f-113">Para facilitar o uso e a sustentabilidade, os nomes devem descrever a função que cada componente executa.</span><span class="sxs-lookup"><span data-stu-id="79b0f-113">For ease of use and maintainability, the names should describe the function that each component performs.</span></span> <span data-ttu-id="79b0f-114">Seguir estas diretrizes de nomeação permite que seus pacotes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sejam documentados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="79b0f-114">Following these naming guidelines allows your [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to be self-documenting.</span></span> <span data-ttu-id="79b0f-115">Outra forma para documentar seus pacotes é usar anotações.</span><span class="sxs-lookup"><span data-stu-id="79b0f-115">Another way to document your packages is by using annotations.</span></span> <span data-ttu-id="79b0f-116">Para obter mais informações sobre anotações, consulte [usar anotações em pacotes](use-annotations-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="79b0f-116">For more information about annotations, see [Use Annotations in Packages](use-annotations-in-packages.md).</span></span>  
  
4.  <span data-ttu-id="79b0f-117">Clique com o botão direito do mouse na tarefa fluxo de dados, clique em **Propriedades**e, na janela Propriedades, verifique se a `LocaleID` propriedade está definida como **Inglês (Estados Unidos)**.</span><span class="sxs-lookup"><span data-stu-id="79b0f-117">Right-click the Data Flow task, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="79b0f-118">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="79b0f-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="79b0f-119">Etapa 5: Adicionar e configurar a fonte de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="79b0f-119">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="79b0f-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79b0f-120">See Also</span></span>  
 [<span data-ttu-id="79b0f-121">Tarefa de Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="79b0f-121">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
