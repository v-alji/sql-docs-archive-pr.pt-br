---
title: 'Etapa 5: Adicionando e configurando a fonte de arquivo simples | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c95ce51-e0fe-4fc5-95eb-2945929f2b13
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 504cfb4bc722627eb8ee70ec1f2c562cef8f1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574132"
---
# <a name="step-5-adding-and-configuring-the-flat-file-source"></a><span data-ttu-id="8b0bd-102">Etapa 5: Adicionar e configurar a fonte de arquivo simples</span><span class="sxs-lookup"><span data-stu-id="8b0bd-102">Step 5: Adding and Configuring the Flat File Source</span></span>
  <span data-ttu-id="8b0bd-103">Nesta tarefa, você irá adicionar e configurar uma fonte de arquivo simples ao seu pacote.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-103">In this task, you will add and configure a Flat File source to your package.</span></span> <span data-ttu-id="8b0bd-104">Uma fonte de arquivo simples é um componente de fluxo de dados que usa metadados definidos por um gerenciador de conexões de arquivo simples para especificar o formato e a estrutura dos dados que serão extraídos do arquivo simples por um processo de transformação.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-104">A Flat File source is a data flow component that uses metadata defined by a Flat File connection manager to specify the format and structure of the data to be extracted from the flat file by a transform process.</span></span> <span data-ttu-id="8b0bd-105">Uma fonte de arquivo simples pode ser configurada para extrair dados de uma única fonte de arquivo simples usando a definição de formato de arquivo fornecida pelo gerenciador de conexões do arquivo simples.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-105">The Flat File source can be configured to extract data from a single flat file by using the file format definition provided by the Flat File connection manager.</span></span>  
  
 <span data-ttu-id="8b0bd-106">Para este tutorial, você configurará a fonte de arquivo simples para usar o `Sample Flat File Source Data` Gerenciador de conexões que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-106">For this tutorial, you will configure the Flat File source to use the `Sample Flat File Source Data` connection manager that you previously created.</span></span>  
  
### <a name="to-add-a-flat-file-source-component"></a><span data-ttu-id="8b0bd-107">Para adicionar um componente Fonte de Arquivo Simples</span><span class="sxs-lookup"><span data-stu-id="8b0bd-107">To add a Flat File Source component</span></span>  
  
1.  <span data-ttu-id="8b0bd-108">Abra o designer de **fluxo de dados** clicando duas vezes na tarefa fluxo de dados `Extract Sample Currency Data` ou clicando na **guia fluxo de dados**.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-108">Open the **Data Flow** designer, either by double-clicking the `Extract Sample Currency Data` data flow task or by clicking the **Data Flow tab**.</span></span>  
  
2.  <span data-ttu-id="8b0bd-109">Na **Caixa de Ferramentas do SSIS**, expanda **Outras Fontes**e arraste uma **Fonte de Arquivo Simples** até a superfície de design da guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="8b0bd-109">In the **SSIS Toolbox**, expand **OtherSources**, and then drag a **Flat File Source** onto the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="8b0bd-110">Na superfície de design do **fluxo de dados** , clique com o botão direito do mouse na **fonte de arquivo simples**recém-adicionada, clique em **renomear**e altere o nome para `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="8b0bd-110">On the **Data Flow** design surface, right-click the newly added **Flat File Source**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
4.  <span data-ttu-id="8b0bd-111">Clique duas vezes na Fonte de Arquivo Simples para abrir a caixa de diálogo Editor da Fonte de Arquivo Simples.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-111">Double-click the Flat File source to open the Flat File Source Editor dialog box.</span></span>  
  
5.  <span data-ttu-id="8b0bd-112">Na caixa **Gerenciador de conexões de arquivo simples** , selecione `Sample Flat File Source Data` .</span><span class="sxs-lookup"><span data-stu-id="8b0bd-112">In the **Flat file connection manager** box, select `Sample Flat File Source Data`.</span></span>  
  
6.  <span data-ttu-id="8b0bd-113">Clique em **Colunas** e verifique se os nomes das colunas estão corretos.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-113">Click **Columns** and verify that the names of the columns are correct.</span></span>  
  
7.  <span data-ttu-id="8b0bd-114">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-114">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="8b0bd-115">Clique com o botão direito do mouse na fonte de Arquivo Simples e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-115">Right-click the Flat File source and click **Properties**.</span></span>  
  
9. <span data-ttu-id="8b0bd-116">No janela Propriedades, verifique se a `LocaleID` propriedade está definida como **inglês (Estados Unidos)**.</span><span class="sxs-lookup"><span data-stu-id="8b0bd-116">In the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8b0bd-117">Próxima tarefa da lição</span><span class="sxs-lookup"><span data-stu-id="8b0bd-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8b0bd-118">Etapa 6: Adicionar e configurar a transformação Pesquisa</span><span class="sxs-lookup"><span data-stu-id="8b0bd-118">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b0bd-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8b0bd-119">See Also</span></span>  
 <span data-ttu-id="8b0bd-120">[Fonte de Arquivo Simples](data-flow/flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="8b0bd-120">[Flat File Source](data-flow/flat-file-source.md) </span></span>  
 [<span data-ttu-id="8b0bd-121">Editor do Gerenciador de Conexões de Arquivos Simples &#40;Página Geral&#41;</span><span class="sxs-lookup"><span data-stu-id="8b0bd-121">Flat File Connection Manager Editor &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
  
