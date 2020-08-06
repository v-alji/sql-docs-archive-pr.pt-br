---
title: Formato de pacote SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cfe0e5dc-5be3-4222-b721-fe83665edd94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 524c65ac5682b8efe8c4191697eb540f9acca82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680556"
---
# <a name="ssis-package-format"></a><span data-ttu-id="4218a-102">Formato do pacote SSIS</span><span class="sxs-lookup"><span data-stu-id="4218a-102">SSIS Package Format</span></span>
  <span data-ttu-id="4218a-103">Na versão atual do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], alterações significativas foram feitas no formato do pacote (arquivo .dtsx) para facilitar a leitura do formato e a comparação dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="4218a-103">In the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], significant changes were made to the package format (.dtsx file) to make it easier to read the format and to compare packages.</span></span> <span data-ttu-id="4218a-104">Você também pode mesclar com mais confiança os pacotes que não contêm alterações conflitantes ou alterações armazenadas em formato binário.</span><span class="sxs-lookup"><span data-stu-id="4218a-104">You can also more reliably merge packages that don't contain conflicting changes or changes stored in binary format.</span></span>  
  
 <span data-ttu-id="4218a-105">Para exibir o formato de arquivo de pacote DTSX atual, consulte [ \[ especificação de formato de arquivo XML de MS-dtsx \] : Data Transformation Services Package](https://go.microsoft.com/fwlink/?LinkId=233251).</span><span class="sxs-lookup"><span data-stu-id="4218a-105">To view the current DTSX package file format, see [\[MS-DTSX\]: Data Transformation Services Package XML File Format Specification](https://go.microsoft.com/fwlink/?LinkId=233251).</span></span>  
  
 <span data-ttu-id="4218a-106">A lista a seguir detalha as alterações no formato de arquivo:</span><span class="sxs-lookup"><span data-stu-id="4218a-106">The following list outlines the file format changes.</span></span> <span data-ttu-id="4218a-107">Para exibir exemplos de códigos dessas alterações, consulte [Alterações do formato de pacote no SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span><span class="sxs-lookup"><span data-stu-id="4218a-107">To view code examples of these changes, see [Package Format Changes in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span></span>  
  
-   <span data-ttu-id="4218a-108">Convenções de formatação foram aplicadas para facilitar a leitura e o entendimento do arquivo .dtsx.</span><span class="sxs-lookup"><span data-stu-id="4218a-108">Formatting conventions have been applied to make it easier to read and understand the .dtsx file.</span></span>  
  
-   <span data-ttu-id="4218a-109">O formato é mais conciso.</span><span class="sxs-lookup"><span data-stu-id="4218a-109">The format is more concise.</span></span> <span data-ttu-id="4218a-110">Elementos separados para cada propriedade foram mantidos como atributos, com exceção de PackageFormatVersion.</span><span class="sxs-lookup"><span data-stu-id="4218a-110">Separate elements for each property have been persisted as attributes, with the exception of the PackageFormatVersion.</span></span> <span data-ttu-id="4218a-111">Os atributos são listados alfabeticamente e as propriedades que têm valores padrão não são mais mantidas.</span><span class="sxs-lookup"><span data-stu-id="4218a-111">Attributes are listed alphabetically, and properties that have default values are no longer persisted.</span></span> <span data-ttu-id="4218a-112">Por fim, os elementos que aparecem várias vezes agora estão contidos em um elemento pai.</span><span class="sxs-lookup"><span data-stu-id="4218a-112">Finally, elements that can appear multiple times, are now contained within a parent element.</span></span>  
  
-   <span data-ttu-id="4218a-113">A maioria dos objetos em um pacote que pode ser referenciada por outros objetos agora tem um atributo `refId` definido no XML do pacote.</span><span class="sxs-lookup"><span data-stu-id="4218a-113">Most objects within a package that can be referred to by other objects now have a `refId` attribute defined in the package XML.</span></span> <span data-ttu-id="4218a-114">Em vez de manter as IDs de linhagem, a `refID` é mantida agora.</span><span class="sxs-lookup"><span data-stu-id="4218a-114">Instead of persisting lineage IDs, the `refID` is now persisted.</span></span> <span data-ttu-id="4218a-115">IDs de linhagem ainda são usadas no runtime e geradas novamente quando o pacote é carregado.</span><span class="sxs-lookup"><span data-stu-id="4218a-115">Lineage IDs are still used within the runtime and regenerated when the package is loaded.</span></span>  
  
     <span data-ttu-id="4218a-116">O valor `refId` é uma cadeia de caracteres exclusiva legível e compreensível, em comparação com GUIDs ou valores inteiros.</span><span class="sxs-lookup"><span data-stu-id="4218a-116">The `refId` value is a unique string that is readable and understandable, compared to GUIDs or integer values.</span></span> <span data-ttu-id="4218a-117">A cadeia de caracteres é semelhante aos valores de caminho usados para configurações de pacote nas versões anteriores do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4218a-117">The string is similar to path values used for package configurations in previous releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="4218a-118">Se você estiver mesclando alterações entre duas versões de um pacote, o `refId` poderá ser usado em operações de localizar/substituir para assegurar que todas as referências a esse objeto tenham sido atualizadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="4218a-118">If you are merging changes between two versions of a package, the `refId` can be used in find/replace operations to ensure that all references to that object have been correctly updated.</span></span>  
  
-   <span data-ttu-id="4218a-119">As informações de layout estão contidas em uma seção CData.</span><span class="sxs-lookup"><span data-stu-id="4218a-119">The layout information is contained in a CData section.</span></span>  
  
-   <span data-ttu-id="4218a-120">As anotações em texto não criptografado são mantidas.</span><span class="sxs-lookup"><span data-stu-id="4218a-120">Annotations are persisted in cleartext.</span></span> <span data-ttu-id="4218a-121">Isso facilita a extração das informações para a geração automática da documentação.</span><span class="sxs-lookup"><span data-stu-id="4218a-121">This makes it easier to extract the information for automated generation of documentation.</span></span>  
  
  
