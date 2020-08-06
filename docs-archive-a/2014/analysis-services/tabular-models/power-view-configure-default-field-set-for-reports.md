---
title: Configurar o conjunto de campos padrão para relatórios de Power View (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- ql12.asvs.bidtoolset.deffieldset.f1
ms.assetid: 6836b42f-28b8-4a98-a86d-2c3c109f0189
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66fbbacd0cc2efd7d379bcc8e68149551476869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679012"
---
# <a name="configure-default-field-set-for-power-view-reports-ssas-tabular"></a><span data-ttu-id="7bf98-102">Configurar conjunto de campo padrão para relatórios de Power View (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="7bf98-102">Configure Default Field Set for Power View Reports (SSAS Tabular)</span></span>
  <span data-ttu-id="7bf98-103">Um conjunto de campo padrão é uma lista predefinida de colunas e medidas que são adicionadas automaticamente a uma tela de relatório do [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] quando a tabela é selecionada na lista de campos de relatório.</span><span class="sxs-lookup"><span data-stu-id="7bf98-103">A default field set is a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span> <span data-ttu-id="7bf98-104">Os autores de modelo de tabela podem criar um campo padrão definido para eliminar etapas redundantes para autores de relatório que usam o modelo para os seus relatórios.</span><span class="sxs-lookup"><span data-stu-id="7bf98-104">Tabular model authors can create a default field set to eliminate redundant steps for report authors who use the model for their reports.</span></span> <span data-ttu-id="7bf98-105">Por exemplo, se você souber que a maioria dos autores de relatório que trabalham com informações de contato de cliente sempre querem ver um nome de contato, um número de telefone principal, um endereço de email e um nome de empresa, poderá pré-selecionar essas colunas para que elas sempre sejam adicionadas à tela de relatório quando o autor clicar na tabela Contato do Cliente.</span><span class="sxs-lookup"><span data-stu-id="7bf98-105">For example, if you know that most report authors who work with customer contact information always want to see a contact name, a primary phone number, an email address, and a company name, you can pre-select those columns so that they are always added to the report canvas when the author clicks the Customer Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bf98-106">Um conjunto de campo padrão só se aplica a um modelo de tabela como um modelo de dados no [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf98-106">A default field set applies only to a tabular model used as a data model in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="7bf98-107">Os conjuntos de campo padrão não têm suporte em relatórios dinâmicos do Excel.</span><span class="sxs-lookup"><span data-stu-id="7bf98-107">Default field sets are not supported in Excel pivot reports.</span></span>  
  
## <a name="creating-a-default-field-set"></a><span data-ttu-id="7bf98-108">Criando um conjunto de campo padrão</span><span class="sxs-lookup"><span data-stu-id="7bf98-108">Creating a Default Field Set</span></span>  
 <span data-ttu-id="7bf98-109">Você pode determinar quais campos, se houver, serão incluídos por padrão sempre que uma tabela específica for selecionada no [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bf98-109">You can determine which fields, if any, are included by default whenever a specific table is selected in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="7bf98-110">Você também pode determinar a ordem na qual os campos aparecem na lista.</span><span class="sxs-lookup"><span data-stu-id="7bf98-110">You can also determine the order in which fields appear in the list.</span></span> <span data-ttu-id="7bf98-111">Para especificar um conjunto de campo padrão, você define propriedades de relatório no projeto de modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="7bf98-111">To specify a default field set, you set report properties in the tabular model project.</span></span>  
  
#### <a name="to-add-a-default-field-set"></a><span data-ttu-id="7bf98-112">Para adicionar um conjunto de campo padrão</span><span class="sxs-lookup"><span data-stu-id="7bf98-112">To add a default field set</span></span>  
  
1.  <span data-ttu-id="7bf98-113">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], clique na tabela (guia) para a qual você está configurando uma lista de campos padrão.</span><span class="sxs-lookup"><span data-stu-id="7bf98-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the table (tab) for which you are configuring a default field list.</span></span>  
  
2.  <span data-ttu-id="7bf98-114">Na janela **Propriedades** , na propriedade **Conjunto de Campo Padrão** , clique em **Clicar para editar**.</span><span class="sxs-lookup"><span data-stu-id="7bf98-114">In the **Properties** window, in the **Default Field Set** property, click **Click to edit**.</span></span>  
  
3.  <span data-ttu-id="7bf98-115">Na caixa de diálogo Conjunto de Campo Padrão, selecione um ou mais campos.</span><span class="sxs-lookup"><span data-stu-id="7bf98-115">In the Default Field Set dialog, select one or more fields.</span></span> <span data-ttu-id="7bf98-116">Você pode escolher qualquer campo na tabela, inclusive medidas.</span><span class="sxs-lookup"><span data-stu-id="7bf98-116">You can choose any field in the table, including measures.</span></span> <span data-ttu-id="7bf98-117">Mantenha a tecla Shift pressionada para selecionar um intervalo ou a tecla Ctrl para selecionar campos individuais.</span><span class="sxs-lookup"><span data-stu-id="7bf98-117">Hold down the Shift key to select a range, or the Ctrl key to select individual fields.</span></span>  
  
4.  <span data-ttu-id="7bf98-118">Clique em **Adicionar** para adicioná-los ao conjunto de campo padrão.</span><span class="sxs-lookup"><span data-stu-id="7bf98-118">Click **Add** to add them to the default field set.</span></span>  
  
5.  <span data-ttu-id="7bf98-119">Use os botões Para cima e Para baixo para especificar uma ordem para a lista de campos.</span><span class="sxs-lookup"><span data-stu-id="7bf98-119">Use the Up and Down buttons to specify an order to the field list.</span></span> <span data-ttu-id="7bf98-120">Os campos serão adicionados ao relatório na ordem definida para o conjunto de campo.</span><span class="sxs-lookup"><span data-stu-id="7bf98-120">Fields will be added to the report in the order defined for the field set.</span></span>  
  
6.  <span data-ttu-id="7bf98-121">Repita estas etapas para outras tabelas em sua pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7bf98-121">Repeat these steps for other tables in your workbook.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="7bf98-122">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7bf98-122">Next Step</span></span>  
 <span data-ttu-id="7bf98-123">Depois que você criar um conjunto de campo padrão, pode influenciar ainda mais a experiência de design de relatório especificando rótulos padrão, imagens padrão, comportamento de grupo padrão, ou se as linhas que contêm o mesmo valor são agrupadas em uma linha ou listadas individualmente.</span><span class="sxs-lookup"><span data-stu-id="7bf98-123">After you create a default field set, you can further influence the report design experience by specifying default labels, default images, default group behavior, or whether rows that contain the same value are grouped together in one row or listed individually.</span></span> <span data-ttu-id="7bf98-124">Para obter mais informações, consulte [Configurar propriedades de comportamento de tabela para relatórios de Power View &#40;SSAS Tabular&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7bf98-124">For more information, see [Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span></span>  
  
  
