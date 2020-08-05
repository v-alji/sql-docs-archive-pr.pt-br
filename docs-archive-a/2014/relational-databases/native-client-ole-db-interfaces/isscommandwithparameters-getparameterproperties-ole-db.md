---
title: ISSCommandWithParameters::GetParameterProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::GetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetParameterProperties method
ms.assetid: 7f4cc5ea-d028-4fe5-9192-bd153ab3c26c
author: rothja
ms.author: jroth
ms.openlocfilehash: 2160c93748375a4aa3bee3d530d441182204134a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572041"
---
# <a name="isscommandwithparametersgetparameterproperties-ole-db"></a><span data-ttu-id="ddeb0-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ddeb0-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="ddeb0-103">Retorna uma matriz de estruturas de conjuntos de propriedades SSPARAMPROPS, um conjunto de propriedades SSPARAMPROPS para cada parâmetro XML ou UDT.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-103">Returns an array of SSPARAMPROPS property set structures, one SSPARAMPROPS property set for each UDT or XML parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddeb0-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ddeb0-104">Syntax</span></span>  
  
```  
  
HRESULT GetParameterProperties(  
DB_UPARAMS *pcParams,  
SSPARAMPROPS **prgParamProperties);  
```  
  
## <a name="arguments"></a><span data-ttu-id="ddeb0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ddeb0-105">Arguments</span></span>  
 <span data-ttu-id="ddeb0-106">*pcParams*[out][in]</span><span class="sxs-lookup"><span data-stu-id="ddeb0-106">*pcParams*[out][in]</span></span>  
 <span data-ttu-id="ddeb0-107">Um ponteiro para a memória que contém o número de estruturas SSPARAMPROPS retornadas em *prgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-107">A pointer to memory that contains the number of SSPARAMPROPS structures returned in *prgParamProperties*.</span></span>  
  
 <span data-ttu-id="ddeb0-108">*prgParamProperties*[out]</span><span class="sxs-lookup"><span data-stu-id="ddeb0-108">*prgParamProperties*[out]</span></span>  
 <span data-ttu-id="ddeb0-109">Um ponteiro para memória na qual uma matriz de estrutura SSPARAMPROPS é retornada.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-109">A pointer to memory in which an array of SSPARAMPROPS structures is returned.</span></span> <span data-ttu-id="ddeb0-110">O provedor aloca memória para as estruturas e retorna o endereço para essa memória; o consumidor libera essa memória com **IMalloc:: Free** quando ela não precisa mais das estruturas.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-110">The provider allocates memory for the structures and returns the address to this memory; the consumer releases this memory with **IMalloc::Free** when it no longer needs the structures.</span></span> <span data-ttu-id="ddeb0-111">Antes de chamar **IMalloc:: Free** para *prgParamProperties*, o consumidor também deve chamar **VariantClear** para a propriedade *vValue* de cada estrutura DBPROP para evitar um vazamento de memória nos casos em que a variante contém um tipo de referência (como um BSTR). Se *pcParams* for zero na saída ou um erro diferente de DB_E_ERRORSOCCURRED ocorrer, o provedor não alocará memória e garantirá que *prgParamProperties* seja um ponteiro nulo na saída.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-111">Before calling **IMalloc::Free** for *prgParamProperties*, the consumer must also call **VariantClear** for the *vValue* property of each DBPROP structure in order to prevent a memory leak in cases where the variant contains a reference type (such as a BSTR.) If *pcParams* is zero on output or an error other than DB_E_ERRORSOCCURRED occurs, the provider does not allocate any memory and ensures that *prgParamProperties* is a null pointer on output.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="ddeb0-112">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="ddeb0-112">Return Code Values</span></span>  
 <span data-ttu-id="ddeb0-113">O método **ParameterProperties** retorna os mesmos códigos de erro que o método principal OLE DB **ICommandProperties:: GetProperties** , exceto que DB_S_ERRORSOCCURRED e DB_E_ERRORSOCCURED não podem ser gerados.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-113">The **GetParameterProperties** method returns the same error codes as the core OLE DB **ICommandProperties::GetProperties** method, except that DB_S_ERRORSOCCURRED and DB_E_ERRORSOCCURED cannot be raised.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddeb0-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="ddeb0-114">Remarks</span></span>  
 <span data-ttu-id="ddeb0-115">**ISSCommandWithParameters:: ParameterProperties** se comporta consistentemente em relação a **GetParameterInfo**.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-115">**ISSCommandWithParameters::GetParameterProperties** behaves consistently with respect to **GetParameterInfo**.</span></span> <span data-ttu-id="ddeb0-116">Se [ISSCommandWithParameters:: ParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) ou **SetParameterInfo** não tiver sido chamado ou tiver sido chamado com cParams igual a zero, **GetParameterInfo** derivará informações de parâmetro e retornará isso.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-116">If [ISSCommandWithParameters::SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) or **SetParameterInfo** have not been called or have been called with cParams equal to zero, **GetParameterInfo** derives parameter information and returns this.</span></span> <span data-ttu-id="ddeb0-117">Se **ISSCommandWithParameters:: ParameterProperties** ou **SetParameterInfo** tiver sido chamado para pelo menos um parâmetro, **ISSCommandWithParameters:: ParameterProperties** retornará propriedades somente para os parâmetros para os quais **ISSCommandWithParameters:: ParameterProperties** foi chamado.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-117">If **ISSCommandWithParameters::SetParameterProperties** or **SetParameterInfo** have been called for at least one parameter, **ISSCommandWithParameters::GetParameterProperties** returns properties only for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span> <span data-ttu-id="ddeb0-118">Se **ISSCommandWithParameters:: ParameterProperties** for chamado após **ISSCommandWithParameters:: ParameterProperties** ou **GetParameterInfo**, as chamadas subsequentes para **ISSCommandWithParameters:: ParameterProperties** retornarão os valores substituídos para esses parâmetros para os quais **ISSCommandWithParameters:: ParameterProperties** foi chamado.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-118">If **ISSCommandWithParameters::SetParameterProperties** is called after **ISSCommandWithParameters::GetParameterProperties** or **GetParameterInfo**, subsequent calls to **ISSCommandWithParameters::GetParameterProperties** return the overridden values for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span>  
  
 <span data-ttu-id="ddeb0-119">A estrutura SSPARAMPROPS é definida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ddeb0-119">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
|<span data-ttu-id="ddeb0-120">Membro</span><span class="sxs-lookup"><span data-stu-id="ddeb0-120">Member</span></span>|<span data-ttu-id="ddeb0-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="ddeb0-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ddeb0-122">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="ddeb0-122">*iOrdinal*</span></span>|<span data-ttu-id="ddeb0-123">O ordinal do parâmetro passado.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-123">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="ddeb0-124">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="ddeb0-124">*cPropertySets*</span></span>|<span data-ttu-id="ddeb0-125">O número de estruturas DBPROPSET em *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-125">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="ddeb0-126">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="ddeb0-126">*rgPropertySets*</span></span>|<span data-ttu-id="ddeb0-127">Um ponteiro para a memória no qual uma matriz de estruturas DBPROPSET deve ser retornada.</span><span class="sxs-lookup"><span data-stu-id="ddeb0-127">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ddeb0-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ddeb0-128">See Also</span></span>  
 [<span data-ttu-id="ddeb0-129">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ddeb0-129">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
