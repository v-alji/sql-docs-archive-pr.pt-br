---
title: Regras de nomenclatura de objeto (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], naming
ms.assetid: b338a60d-4802-4b68-862a-6dc6a3f75e48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adfd4b23b6fe9129641271fc3c2381e161119ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87581537"
---
# <a name="object-naming-rules-analysis-services"></a><span data-ttu-id="98258-102">Regras de nomenclatura de objeto (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="98258-102">Object Naming Rules (Analysis Services)</span></span>
  <span data-ttu-id="98258-103">Este tópico descreve as convenções de nomenclatura de objeto, bem como as palavras e os caracteres reservados que não podem ser usados em nomes de objetos, códigos ou scripts no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98258-103">This topic describes object naming conventions, as well as the reserved words and characters that cannot be used in any object name, in code or script in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
##  <a name="naming-conventions"></a><a name="bkmk_Names"></a><span data-ttu-id="98258-104">Convenções de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="98258-104">Naming Conventions</span></span>  
 <span data-ttu-id="98258-105">Todo objeto tem as propriedades `Name` e `ID` que devem ser exclusivas no escopo da coleção pai.</span><span class="sxs-lookup"><span data-stu-id="98258-105">Every object has a `Name` and `ID` property that must be unique within the scope of the parent collection.</span></span> <span data-ttu-id="98258-106">Por exemplo, duas dimensões podem ter o mesmo nome, desde que cada uma resida em um banco de dados diferente.</span><span class="sxs-lookup"><span data-stu-id="98258-106">For example, two dimensions can have same name as long as each one resides in a different database.</span></span>  
  
 <span data-ttu-id="98258-107">Embora você possa especificar isso manualmente, a `ID` costuma ser gerada automaticamente quando o objeto é criado.</span><span class="sxs-lookup"><span data-stu-id="98258-107">Although you can specify it manually, the `ID` is typically auto-generated when the object is created.</span></span> <span data-ttu-id="98258-108">Após começar a criar um modelo, nunca altere a `ID`.</span><span class="sxs-lookup"><span data-stu-id="98258-108">You should never change the `ID` once you have begun building a model.</span></span> <span data-ttu-id="98258-109">Todas as referências de objeto em um modelo se baseiam na `ID`.</span><span class="sxs-lookup"><span data-stu-id="98258-109">All object references throughout a model are based on the `ID`.</span></span> <span data-ttu-id="98258-110">Então, a alteração de uma `ID` pode facilmente resultar na corrupção do modelo.</span><span class="sxs-lookup"><span data-stu-id="98258-110">Thus, changing an `ID` can easily result in model corruption.</span></span>  
  
 <span data-ttu-id="98258-111">Os objetos `DataSource` e `DataSourceView` têm exceções consideráveis para convenções de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="98258-111">`DataSource` and `DataSourceView` objects have notable exceptions to naming conventions.</span></span> <span data-ttu-id="98258-112">A ID `DataSource` pode ser definida como um único ponto (.), que não é exclusivo, como referência ao banco de dados atual.</span><span class="sxs-lookup"><span data-stu-id="98258-112">`DataSource` ID can be set to a single dot (.), which is not unique, as a reference to the current database.</span></span> <span data-ttu-id="98258-113">Uma segunda exceção é `DataSourceView`, que cumpre as convenções de nomenclatura definidas por objetos `DataSet` no .NET Framework, onde o `Name` é usado como o identificador.</span><span class="sxs-lookup"><span data-stu-id="98258-113">A second exception is `DataSourceView`, which adheres to the naming conventions defined for `DataSet` objects in the .NET Framework, where the `Name` is used as the identifier.</span></span>  
  
 <span data-ttu-id="98258-114">As regras a seguir se aplicam às propriedades `Name` e `ID`.</span><span class="sxs-lookup"><span data-stu-id="98258-114">The following rules apply to `Name` and `ID` properties.</span></span>  
  
-   <span data-ttu-id="98258-115">Os nomes não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="98258-115">Names are case insensitive.</span></span> <span data-ttu-id="98258-116">Você não pode ter um cubo chamado "Sales" e outro chamado "Sales" no mesmo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="98258-116">You cannot have a cube named "sales" and another named "Sales" in the same database.</span></span>  
  
-   <span data-ttu-id="98258-117">Não são permitidos espaços à esquerda ou à direita em um nome de objeto, embora você possa inserir espaços em um nome.</span><span class="sxs-lookup"><span data-stu-id="98258-117">No leading or trailing spaces allowed in an object name, although you can embed spaces within a name.</span></span> <span data-ttu-id="98258-118">Os espaços de abertura e fechamento são eliminados implicitamente.</span><span class="sxs-lookup"><span data-stu-id="98258-118">Leading and trailing spaces are implicitly trimmed.</span></span> <span data-ttu-id="98258-119">Isso se aplica a `Name` e `ID` de um objeto.</span><span class="sxs-lookup"><span data-stu-id="98258-119">This applies to both the `Name` and `ID` of an object.</span></span>  
  
-   <span data-ttu-id="98258-120">O número máximo de caracteres é 100.</span><span class="sxs-lookup"><span data-stu-id="98258-120">The maximum number of characters is 100.</span></span>  
  
-   <span data-ttu-id="98258-121">Não há nenhum requisito especial para o primeiro caractere de um identificador.</span><span class="sxs-lookup"><span data-stu-id="98258-121">There is no special requirement for the first character of an identifier.</span></span> <span data-ttu-id="98258-122">O primeiro caractere pode ser qualquer caractere válido.</span><span class="sxs-lookup"><span data-stu-id="98258-122">The first character may be any valid character.</span></span>  
  
##  <a name="reserved-words-and-characters"></a><a name="bkmk_reserved"></a><span data-ttu-id="98258-123">Palavras reservadas e caracteres</span><span class="sxs-lookup"><span data-stu-id="98258-123">Reserved Words and Characters</span></span>  
 <span data-ttu-id="98258-124">As palavras reservadas estão em inglês e se aplicam a nomes de objetos, e não a legendas.</span><span class="sxs-lookup"><span data-stu-id="98258-124">Reserved words are in English, and apply to object names, not Captions.</span></span> <span data-ttu-id="98258-125">Se você usar inadvertidamente uma palavra reservada em um nome de objeto, ocorrerá um erro de validação.</span><span class="sxs-lookup"><span data-stu-id="98258-125">If you inadvertently use a reserved word in an object name, a validation error will occur.</span></span> <span data-ttu-id="98258-126">Nos modelos multidimensionais e de mineração de dados, as palavras reservadas descritas a seguir não podem ser usadas em qualquer objeto, a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="98258-126">For multidimensional and data mining models, the reserved words described below cannot be used in any object name, at any time.</span></span>  
  
 <span data-ttu-id="98258-127">Em modelos de tabela, em que a compatibilidade do banco de dados é definida como 1103, as regras de validação foram atenuadas para certos objetos, fora de conformidade para os requisitos de caracteres estendidos e convenções de nomenclatura de determinados aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="98258-127">For tabular models, where the database compatibility is set to 1103, validation rules have been relaxed for certain objects, out of compliance for the extended character requirements and naming conventions of certain client applications.</span></span> <span data-ttu-id="98258-128">Os bancos de dados que atendem a esses critérios estão sujeitos a regras de validação menos rigorosas.</span><span class="sxs-lookup"><span data-stu-id="98258-128">Databases that meet these criteria are subject to less stringent validation rules.</span></span> <span data-ttu-id="98258-129">Nesse caso, é possível que um nome de objeto inclua um caractere restrito e ainda passe na validação.</span><span class="sxs-lookup"><span data-stu-id="98258-129">In this case, it's possible for an object name to include a restricted character and still pass validation.</span></span>  
  
 <span data-ttu-id="98258-130">**Palavras reservadas**</span><span class="sxs-lookup"><span data-stu-id="98258-130">**Reserved Words**</span></span>  
  
-   <span data-ttu-id="98258-131">AUX</span><span class="sxs-lookup"><span data-stu-id="98258-131">AUX</span></span>  
  
-   <span data-ttu-id="98258-132">CLOCK$</span><span class="sxs-lookup"><span data-stu-id="98258-132">CLOCK$</span></span>  
  
-   <span data-ttu-id="98258-133">COM1 a COM9 (COM1, COM2, COM3 e assim por diante)</span><span class="sxs-lookup"><span data-stu-id="98258-133">COM1 through COM9 (COM1, COM2, COM3, and so on)</span></span>  
  
-   <span data-ttu-id="98258-134">CON</span><span class="sxs-lookup"><span data-stu-id="98258-134">CON</span></span>  
  
-   <span data-ttu-id="98258-135">LPT1 a LPT9 (LPT1, LPT2, LPT3 e assim por diante)</span><span class="sxs-lookup"><span data-stu-id="98258-135">LPT1 through LPT9 (LPT1, LPT2, LPT3, and so on)</span></span>  
  
-   <span data-ttu-id="98258-136">NUL</span><span class="sxs-lookup"><span data-stu-id="98258-136">NUL</span></span>  
  
-   <span data-ttu-id="98258-137">PRN</span><span class="sxs-lookup"><span data-stu-id="98258-137">PRN</span></span>  
  
-   <span data-ttu-id="98258-138">NULL não é permitido como um caractere em qualquer cadeia de caracteres dentro do XML</span><span class="sxs-lookup"><span data-stu-id="98258-138">NULL is not allowed as a character in any string within the XML</span></span>  
  
 <span data-ttu-id="98258-139">**Caracteres reservados**</span><span class="sxs-lookup"><span data-stu-id="98258-139">**Reserved Characters**</span></span>  
  
 <span data-ttu-id="98258-140">A tabela a seguir lista caracteres inválidos para objetos específicos.</span><span class="sxs-lookup"><span data-stu-id="98258-140">The following table lists invalid characters for specific objects.</span></span>  
  
|<span data-ttu-id="98258-141">Objeto</span><span class="sxs-lookup"><span data-stu-id="98258-141">Object</span></span>|<span data-ttu-id="98258-142">Caracteres inválidos</span><span class="sxs-lookup"><span data-stu-id="98258-142">Invalid characters</span></span>|  
|------------|------------------------|  
|`Server`|<span data-ttu-id="98258-143">Ao nomear um objeto de servidor, siga as convenções de nomenclatura de servidor do Windows.</span><span class="sxs-lookup"><span data-stu-id="98258-143">Follow Windows server naming conventions when naming a server object.</span></span> <span data-ttu-id="98258-144">Para obter detalhes, consulte [Convenções de nomenclatura (Windows)](/windows/desktop/DNS/naming-conventions) .</span><span class="sxs-lookup"><span data-stu-id="98258-144">See [Naming Conventions (Windows)](/windows/desktop/DNS/naming-conventions) for details.</span></span>|  
|`DataSource`| `: / \ * \| ? " () [] {} <>` |  
|<span data-ttu-id="98258-145">`Level` ou `Attribute`</span><span class="sxs-lookup"><span data-stu-id="98258-145">`Level` or `Attribute`</span></span>|````. , ; ' ` : / \ * & \| ? " & % $ ! + = [] {} < >````|  
|<span data-ttu-id="98258-146">`Dimension` ou `Hierarchy`</span><span class="sxs-lookup"><span data-stu-id="98258-146">`Dimension` or `Hierarchy`</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} <,>````|  
|<span data-ttu-id="98258-147">Todos os outros objetos</span><span class="sxs-lookup"><span data-stu-id="98258-147">All other objects</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} < >````|  
  
 <span data-ttu-id="98258-148">**Exceções: Quando caracteres reservados são permitidos**</span><span class="sxs-lookup"><span data-stu-id="98258-148">**Exceptions: When Reserved Characters are Allowed**</span></span>  
  
 <span data-ttu-id="98258-149">Conforme observado, os bancos de dados de uma modalidade e de um nível de compatibilidade específicos podem ter nomes de objetos que incluam caracteres reservados.</span><span class="sxs-lookup"><span data-stu-id="98258-149">As noted, databases of a specific modality and compatibility level can have object names that include reserved characters.</span></span> <span data-ttu-id="98258-150">Os nomes de objeto de atributo de dimensão, hierarquia, nível, medida e KPI podem incluir caracteres reservados, para bancos de dados de tabelas (1103 ou superior) que permitem o uso de caracteres estendidos:</span><span class="sxs-lookup"><span data-stu-id="98258-150">Dimension attribute, hierarchy, level, measure and KPI object names can include reserved characters, for tabular databases (1103 or higher) that allow the use of extended characters:</span></span>  
  
|<span data-ttu-id="98258-151">Modo de servidor e nível de compatibilidade de banco de dados</span><span class="sxs-lookup"><span data-stu-id="98258-151">Server mode and database compatibility level</span></span>|<span data-ttu-id="98258-152">Caracteres reservados permitidos?</span><span class="sxs-lookup"><span data-stu-id="98258-152">Reserved characters allowed?</span></span>|  
|--------------------------------------------------|----------------------------------|  
|<span data-ttu-id="98258-153">MOLAP (todas as versões)</span><span class="sxs-lookup"><span data-stu-id="98258-153">MOLAP (all versions)</span></span>|<span data-ttu-id="98258-154">Não</span><span class="sxs-lookup"><span data-stu-id="98258-154">No</span></span>|  
|<span data-ttu-id="98258-155">Tabela - 1050</span><span class="sxs-lookup"><span data-stu-id="98258-155">Tabular - 1050</span></span>|<span data-ttu-id="98258-156">Não</span><span class="sxs-lookup"><span data-stu-id="98258-156">No</span></span>|  
|<span data-ttu-id="98258-157">Tabela - 1100</span><span class="sxs-lookup"><span data-stu-id="98258-157">Tabular - 1100</span></span>|<span data-ttu-id="98258-158">Não</span><span class="sxs-lookup"><span data-stu-id="98258-158">No</span></span>|  
|<span data-ttu-id="98258-159">Tabular-1130 e superior</span><span class="sxs-lookup"><span data-stu-id="98258-159">Tabular - 1130 and higher</span></span>|<span data-ttu-id="98258-160">Sim</span><span class="sxs-lookup"><span data-stu-id="98258-160">Yes</span></span>|  
  
 <span data-ttu-id="98258-161">Bancos de dados podem ter um ModelType padrão.</span><span class="sxs-lookup"><span data-stu-id="98258-161">Databases can have a ModelType of default.</span></span> <span data-ttu-id="98258-162">O padrão é equivalente a multidimensional e, portanto, não dá suporte ao uso de caracteres reservados em nomes de colunas.</span><span class="sxs-lookup"><span data-stu-id="98258-162">Default is equivalent to multidimensional, and thus does not support the use of reserved characters in column names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98258-163">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="98258-163">See Also</span></span>  
 <span data-ttu-id="98258-164">[Palavras reservadas MDX](/sql/mdx/mdx-reserved-words) </span><span class="sxs-lookup"><span data-stu-id="98258-164">[MDX Reserved Words](/sql/mdx/mdx-reserved-words) </span></span>  
 <span data-ttu-id="98258-165">[Conversões &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span><span class="sxs-lookup"><span data-stu-id="98258-165">[Translations &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span></span>  
 [<span data-ttu-id="98258-166">Conformidade XML for Analysis &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="98258-166">XML for Analysis Compliance &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-compliance-xmla)  
  
  
