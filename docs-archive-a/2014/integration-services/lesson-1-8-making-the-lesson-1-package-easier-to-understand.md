---
title: 'Etapa 8: Tornando o pacote da Lição 1 mais fácil de compreender | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e3751e53-77c7-47d0-8fe8-73ed1a53413a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fb8e2adb9062b5b777acc14df0ddc5b45884ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574128"
---
# <a name="step-8-making-the-lesson-1-package-easier-to-understand"></a><span data-ttu-id="d303f-102">Etapa 8: Tornar o pacote da Lição 1 mais fácil de compreender</span><span class="sxs-lookup"><span data-stu-id="d303f-102">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>
  <span data-ttu-id="d303f-103">Agora que você concluiu a configuração do pacote da Lição 1, é uma boa ideia verificar o layout do pacote.</span><span class="sxs-lookup"><span data-stu-id="d303f-103">Now that you have completed the configuration of the Lesson 1 package, it is a good idea to tidy up the package layout.</span></span> <span data-ttu-id="d303f-104">Se as formas dos layouts de controle e dos fluxos de dados são de tamanhos aleatórias ou se as formas não estão alinhadas ou agrupadas, a funcionalidade de pacote pode ser mais difícil de ser entendida.</span><span class="sxs-lookup"><span data-stu-id="d303f-104">If the shapes in the control and data flow layouts are random sizes, or if the shapes are not aligned or grouped, the functionality of package can be more difficult to understand.</span></span>  
  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="d303f-105">fornecem recursos que facilitam e agilizam a formatação do layout do pacote.</span><span class="sxs-lookup"><span data-stu-id="d303f-105">Data Tools provides tools that make it easy and quick to format the package layout.</span></span> <span data-ttu-id="d303f-106">Os recursos de formatação incluem a capacidade de criar formas do mesmo tamanho, alinhar formas e manipular o espaçamento horizontal e vertical entre os espaçamentos.</span><span class="sxs-lookup"><span data-stu-id="d303f-106">The formatting features include the ability to make shapes the same size, align shapes, and manipulate the horizontal and vertical spacing between shapes.</span></span>  
  
 <span data-ttu-id="d303f-107">Outro modo para melhorar a compreensão de funcionalidade de pacote é adicionar anotações que descrevem a funcionalidade do pacote.</span><span class="sxs-lookup"><span data-stu-id="d303f-107">Another way to improve the understanding of package functionality is to add annotations that describe package functionality.</span></span>  
  
 <span data-ttu-id="d303f-108">Nesta tarefa, você utilizará os recursos de formatação nas ferramentas de dados do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para melhorar o layout do fluxo de dados e também adicionar uma anotação ao fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="d303f-108">In this task, you will use the formatting features in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools to improve the layout of the data flow and also add an annotation to the data flow.</span></span>  
  
### <a name="to-format-the-layout-of-the-data-flow"></a><span data-ttu-id="d303f-109">Para formatar o layout do fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d303f-109">To format the layout of the data flow</span></span>  
  
1.  <span data-ttu-id="d303f-110">Se o pacote da Lição 1 ainda não estiver aberto, no Gerenciador de Soluções, clique duas vezes em Lição 1.dtsx.</span><span class="sxs-lookup"><span data-stu-id="d303f-110">If the Lesson 1 package is not already open, double-click Lesson 1.dtsx in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="d303f-111">Clique na guia **Fluxo de Dados** .</span><span class="sxs-lookup"><span data-stu-id="d303f-111">Click the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="d303f-112">Posicione o cursor na parte superior e à direita da transformação Extrair Moeda de Exemplo e clique e arraste o cursor por todos os componentes do fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="d303f-112">Place the cursor to the top and to the right of the Extract Sample Currency transformation, click, and then drag the cursor across all the data flow components.</span></span>  
  
4.  <span data-ttu-id="d303f-113">No menu **Formatar** , aponte para **Igualar Tamanho**e clique em **Ambos**.</span><span class="sxs-lookup"><span data-stu-id="d303f-113">On the **Format** menu, point to **Make Same Size**, and then click **Both**.</span></span>  
  
5.  <span data-ttu-id="d303f-114">Com os objetos de fluxo de dados selecionados, no menu **Formatar** , aponte para **Alinhar**e clique em **À esquerda**.</span><span class="sxs-lookup"><span data-stu-id="d303f-114">With the data flow objects selected, on the **Format** menu, point to **Align**, and then click **Lefts**.</span></span>  
  
### <a name="to-add-an-annotation-to-the-data-flow"></a><span data-ttu-id="d303f-115">Para adicionar uma anotação ao fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="d303f-115">To add an annotation to the data flow</span></span>  
  
1.  <span data-ttu-id="d303f-116">Clique com o botão direito do mouse em qualquer lugar da tela de fundo da superfície de design do fluxo de dados e clique em **Adicionar Anotação**.</span><span class="sxs-lookup"><span data-stu-id="d303f-116">Right-click anywhere in the background of the data flow design surface and then click **Add Annotation**.</span></span>  
  
2.  <span data-ttu-id="d303f-117">Digite ou cole o texto a seguir na caixa de anotação.</span><span class="sxs-lookup"><span data-stu-id="d303f-117">Type or paste the following text in the annotation box.</span></span>  
  
     <span data-ttu-id="d303f-118">**O fluxo de dados extrai os dados de um arquivo, pesquisa valores na coluna CurrencyKey da tabela DimCurrency e na coluna DateKey da tabela DimDate, além de gravar os dados na tabela NewFactCurrencyRate.**</span><span class="sxs-lookup"><span data-stu-id="d303f-118">**The data flow extracts data from a file, looks up values in the CurrencyKey column in the DimCurrency table and the DateKey column in the DimDate table, and writes the data to the NewFactCurrencyRate table.**</span></span>  
  
     <span data-ttu-id="d303f-119">Para usar a quebra de linhas no texto da caixa de anotação, posicione o cursor no local em que deseja começar uma nova linha e pressione a tecla Enter.</span><span class="sxs-lookup"><span data-stu-id="d303f-119">To wrap the text in the annotation box, place the cursor where you want to start a new line and press the Enter key.</span></span>  
  
     <span data-ttu-id="d303f-120">Se você não inserir um texto na caixa de anotação, essa caixa desaparecerá ao clicar fora dela.</span><span class="sxs-lookup"><span data-stu-id="d303f-120">If you do not add text to the annotation box, it disappears when you click outside the box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d303f-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d303f-121">Next Steps</span></span>  
 [<span data-ttu-id="d303f-122">Etapa 9: Testar o pacote de tutorial da Lição 1</span><span class="sxs-lookup"><span data-stu-id="d303f-122">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](../integration-services/lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
  
