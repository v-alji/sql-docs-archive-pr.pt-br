---
title: Representação em perspectiva (tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 6d2636c4-dae4-448f-a1d4-dbee739e177c
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca8a66d3134748fd524dc0c6b524d944213533e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572230"
---
# <a name="perspective-representation-tabular"></a><span data-ttu-id="d5cc2-102">Representação de perspectiva (de tabela)</span><span class="sxs-lookup"><span data-stu-id="d5cc2-102">Perspective Representation (Tabular)</span></span>
  <span data-ttu-id="d5cc2-103">Uma perspectiva é um mecanismo para simplificar ou focar o modelo em uma parte menor dele para o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-103">A perspective is a mechanism to simplify or focus the model into a smaller portion of it for the client application.</span></span>  
  
 <span data-ttu-id="d5cc2-104">Consulte [representação em perspectiva (tabular)](perspective-representation-tabular.md) para obter uma explicação detalhada sobre como criar e manipular a representação de perspectiva.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-104">See [Perspective Representation (Tabular)](perspective-representation-tabular.md) for a detailed explanation on how to create and manipulate the perspective representation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="d5cc2-105">Perspectivas não são um mecanismo de segurança; objetos fora da perspectiva ainda podem ser acessados pelo usuário através de outras interfaces.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-105">Perspectives are not a security mechanism; objects outside the perspective can still be accessed by the user through other interfaces.</span></span>  
  
## <a name="perspective-representation"></a><span data-ttu-id="d5cc2-106">Representação de perspectiva</span><span class="sxs-lookup"><span data-stu-id="d5cc2-106">Perspective Representation</span></span>  
 <span data-ttu-id="d5cc2-107">Em termos de objetos AMO, uma representação de perspectiva tem uma relação de mapeamento de um para um com <xref:Microsoft.AnalysisServices.Perspective> e nenhum outro objeto AMO principal é necessário.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-107">In terms of AMO objects a perspective representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Perspective> and no other main AMO objects are required.</span></span>  
  
### <a name="perspective-in-amo"></a><span data-ttu-id="d5cc2-108">Perspectiva no AMO</span><span class="sxs-lookup"><span data-stu-id="d5cc2-108">Perspective in AMO</span></span>  
 <span data-ttu-id="d5cc2-109">O snippet de código a seguir mostra como criar uma perspectiva em um modelo de tabela.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-109">The following code snippet shows how to create a perspective in a Tabular model.</span></span> <span data-ttu-id="d5cc2-110">O elemento chave neste pedaço de código é o perspectiveElements; este objeto é uma representação gráfica de todos os objetos no modelo de tabela que são expostos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-110">The key element in this piece of code is the perspectiveElements; this object is a graphical representation of all the objects in the tabular model that are exposed to the user.</span></span> <span data-ttu-id="d5cc2-111">*perspectiveElements* contém 4 colunas e, para esse cenário, somente as colunas 1, 2 e 3 são relevantes.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-111">*perspectiveElements* contains 4 columns and for this scenario only columns 1, 2 and 3 are relevant.</span></span> <span data-ttu-id="d5cc2-112">A Coluna 1 contém o tipo de elemento exibido - elementTypeValue -; a coluna 2 contém o nome completo do elemento--, que provavelmente precisará ser analisado para inserir o elemento na perspectiva; a coluna 3 contém um item de caixa de seleção - checkedElement - que diz se o elemento faz parte da perspectiva ou não.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-112">Column 1 contains the type of element displayed -elementTypeValue-; column 2 contains the complete name of the element --, that probably will need to parsed to enter the element in the perspective; column 3 contains a checkbox item -checkedElement- that tells if the element is part of the perspective or not.</span></span>  
  
```  
  
private void updatePerspective_Click(  
                     AMO.Cube modelCube  
                  ,  DataGridView perspectiveElements  
                  ,  string updatedPerspectiveID  
             )  
{  
    //Update is done by delete first, create new and insert after  
    //if perspective doesn't exist then create first and insert after  
    updatedPerspectiveID = updatedPerspectiveID.Trim();  
    if (modelCube.Perspectives.Contains(updatedPerspectiveID))  
    {  
        modelCube.Perspectives.Remove(updatedPerspectiveID, true);  
        newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    }  
    AMO.Perspective currentPerspective = modelCube.Perspectives.Add(updatedPerspectiveID, updatedPerspectiveID);  
  
    foreach (DataGridViewRow currentDGVRow in perspectiveElements.Rows)  
    {  
        bool checkedElement = (bool)currentDGVRow.Cells[3].Value;  
        if (checkedElement)  
        {  
            string elementTypeValue = currentDGVRow.Cells[1].Value.ToString();  
            string elementNameValue = currentDGVRow.Cells[2].Value.ToString();  
            switch (elementTypeValue)  
            {  
                case "Column: Attribute":  
                case "Column: Calculated Column":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionAttributeName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Attributes.Contains(perspectiveDimensionAttributeName))  
                        {  
                            currentPerspectiveDimension.Attributes.Add(perspectiveDimensionAttributeName);  
                        }  
                    }  
                    break;  
                case "Hierarchy":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionHierarchyName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Hierarchies.Contains(perspectiveDimensionHierarchyName))  
                        {  
                            currentPerspectiveDimension.Hierarchies.Add(perspectiveDimensionHierarchyName);  
                        }  
                    }  
                    break;  
                case "Measure":  
                    {  
                        string perspectiveMeasureGroupName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string measureName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        string perspectiveMeasureName = string.Format("[Measures].[{0}]", measureName);  
                        AMO.PerspectiveCalculation currentPerspectiveCalculation = new AMO.PerspectiveCalculation(perspectiveMeasureName, AMO.PerspectiveCalculationType.Member);  
                        if (!currentPerspective.Calculations.Contains(perspectiveMeasureName))  
                        {  
                            currentPerspective.Calculations.Add(currentPerspectiveCalculation);  
                        }  
                        if (modelCube.MdxScripts["MdxScript"].CalculationProperties.Contains(string.Format("KPIs.[{0}]", measureName)))  
                        {//Current Measure is also a KPI ==> will be added to the KPIs collection of the perspective  
                            AMO.PerspectiveKpi currentPerspectiveKpi = new AMO.PerspectiveKpi(perspectiveMeasureName);  
                            if (!currentPerspective.Kpis.Contains(perspectiveMeasureName))  
                            {  
                                currentPerspective.Kpis.Add(currentPerspectiveKpi);  
                            }  
                        }  
                    }  
                    break;  
                default:  
                    break;  
            }  
        }  
    }  
  
    newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.CreateOrReplace);  
    MessageBox.Show(String.Format("Perpective successfully updated."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="d5cc2-113">Exemplo de AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="d5cc2-113">AMO2Tabular sample</span></span>  
 <span data-ttu-id="d5cc2-114">No entanto, para compreender como usar o AMO para criar e manipular representações de perspectiva, consulte o código-fonte do exemplo “AMO para Tabela”.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-114">However, to have an understanding on how to use AMO to create and manipulate perspective representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="d5cc2-115">O exemplo está disponível no Codeplex.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-115">The sample is available at Codeplex.</span></span> <span data-ttu-id="d5cc2-116">Uma nota importante sobre o código: o código é fornecido apenas como um suporte aos conceitos lógicos explicados aqui; ele não deve ser usado em um ambiente de produção, nem para fins que não sejam pedagógicos.</span><span class="sxs-lookup"><span data-stu-id="d5cc2-116">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
