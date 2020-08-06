---
title: ISSCommandWithParameters::SetParameterProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::SetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- SetParameterProperties method
ms.assetid: 4cd0281a-a2a0-43df-8e46-eb478b64cb4b
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bf8e5cde9885a5d9b55d84c6384b76aecf50b8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679333"
---
# <a name="isscommandwithparameterssetparameterproperties-ole-db"></a><span data-ttu-id="b4557-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="b4557-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="b4557-103">Define as propriedades de cada parâmetro por ordinal ou define as propriedades de parâmetro em massa especificando uma matriz de estruturas SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="b4557-103">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of SSPARAMPROPS structures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4557-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b4557-104">Syntax</span></span>  
  
```  
  
HRESULT SetParameterProperties(  
DB_UPARAMS cParams,   
SSPARAMPROPS rgParamProperties[]);  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4557-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b4557-105">Arguments</span></span>  
 <span data-ttu-id="b4557-106">*cParams*[in]</span><span class="sxs-lookup"><span data-stu-id="b4557-106">*cParams*[in]</span></span>  
 <span data-ttu-id="b4557-107">O número de estruturas SSPARAMPROPS na matriz *rgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="b4557-107">The number of SSPARAMPROPS structures in the *rgParamProperties* array.</span></span> <span data-ttu-id="b4557-108">Se esse número for zero, o `ISSCommandWithParameters::SetParameterProperties` excluirá todas as propriedades que podem ter sido especificadas para qualquer parâmetro no comando.</span><span class="sxs-lookup"><span data-stu-id="b4557-108">If this number is zero, `ISSCommandWithParameters::SetParameterProperties` will delete all properties that might have been specified for any parameters in the command.</span></span>  
  
 <span data-ttu-id="b4557-109">*rgParamProperties*[in]</span><span class="sxs-lookup"><span data-stu-id="b4557-109">*rgParamProperties*[in]</span></span>  
 <span data-ttu-id="b4557-110">Uma matriz de estruturas SSPARAMPROPS a ser definida.</span><span class="sxs-lookup"><span data-stu-id="b4557-110">An array of SSPARAMPROPS structures to be set.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="b4557-111">Valores do código de retorno</span><span class="sxs-lookup"><span data-stu-id="b4557-111">Return Code Values</span></span>  
 <span data-ttu-id="b4557-112">O `ISSCommandWithParameters::SetParameterProperties` método retorna os mesmos códigos de erro que o método principal OLE DB **ICommandProperties:: SetProperties** .</span><span class="sxs-lookup"><span data-stu-id="b4557-112">The `ISSCommandWithParameters::SetParameterProperties` method returns the same error codes as the core OLE DB **ICommandProperties::SetProperties** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4557-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="b4557-113">Remarks</span></span>  
 <span data-ttu-id="b4557-114">A definição de propriedades de parâmetro com esse método é permitida por parâmetro por ordinal ou com uma chamada única `ISSCommandWithParameters::SetParameterProperties` depois que o SSPARAMPROPS tiver sido criado a partir da matriz de propriedades.</span><span class="sxs-lookup"><span data-stu-id="b4557-114">Setting parameter properties with this method is allowed on a per parameter basis by ordinal, or with a single `ISSCommandWithParameters::SetParameterProperties` call once the SSPARAMPROPS has been built from the property array.</span></span>  
  
 <span data-ttu-id="b4557-115">O método **SetParameterInfo** deve ser chamado antes de chamar o `ISSCommandWithParameters::SetParameterProperties` método.</span><span class="sxs-lookup"><span data-stu-id="b4557-115">The **SetParameterInfo** method must be called before calling the `ISSCommandWithParameters::SetParameterProperties` method.</span></span> <span data-ttu-id="b4557-116">Se você chamar `SetParameterProperties(0, NULL)` limpará todas as propriedades de parâmetro especificadas, ao passo que se chamar `SetParameterInfo(0,NULL,NULL)`, limpará todas as informações do parâmetro incluindo as propriedades que podem ser associadas a um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b4557-116">Calling `SetParameterProperties(0, NULL)` clears all specified parameter properties, while calling `SetParameterInfo(0,NULL,NULL)` clears all the parameter info including any properties that might be associated with a parameter.</span></span>  
  
 <span data-ttu-id="b4557-117">Chamar `ISSCommandWithParameters::SetParameterProperties` para especificar propriedades para um parâmetro que não é do tipo DBTYPE_XML ou DBTYPE_UDT retorna DB_E_ERRORSOCCURRED ou DB_S_ERRORSOCCURRED e marca o campo *dwStatus* de todas as DBPROPs contidas em SSPARAMPROPS para esse parâmetro com DBPROPSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="b4557-117">Calling `ISSCommandWithParameters::SetParameterProperties` to specify properties for a parameter which is not of type DBTYPE_XML or DBTYPE_UDT returns DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED and marks the *dwStatus* field of all DBPROPs contained in SSPARAMPROPS for that parameter with DBPROPSTATUS_NOTSET.</span></span> <span data-ttu-id="b4557-118">A matriz DBPROP de cada DBPROPSET contido em SSPARAMPROPS deveria ser atravessada para detectar o parâmetro ao qual DB_E_ERRORSOCCURRED ou DB_S_ERRORSOCCURRED se refere.</span><span class="sxs-lookup"><span data-stu-id="b4557-118">The DBPROP array of each DBPROPSET contained in SSPARAMPROPS should be traversed to detect which parameter the DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED refers to.</span></span>  
  
 <span data-ttu-id="b4557-119">Se `ISSCommandWithParameters::SetParameterProperties` for chamado para especificar as propriedades de parâmetros cujas informações de parâmetro ainda não foram definidas com **SetParameterInfo**, o provedor retornará E_UNEXPECTED com a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="b4557-119">If `ISSCommandWithParameters::SetParameterProperties` is called to specify the properties of parameters whose parameter info have not been set yet with **SetParameterInfo**, the provider returns E_UNEXPECTED with the following error message:</span></span>  
  
 <span data-ttu-id="b4557-120">O método SetParameterProperties não pode ser chamado para os parâmetros especificados sem primeiro chamar o método SetParameterInfo.</span><span class="sxs-lookup"><span data-stu-id="b4557-120">SetParameterProperties method cannot be called for the specified parameters without first calling SetParameterInfo method.</span></span> <span data-ttu-id="b4557-121">As informações de parâmetro devem ser definidas antes da definição das propriedades de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b4557-121">The parameter information must be set before setting the parameter properties.</span></span>  
  
 <span data-ttu-id="b4557-122">Se a chamada para `ISSCommandWithParameters::SetParameterProperties` contiver alguns parâmetros em que as informações de parâmetro foram definidas, e alguns parâmetros em que as informações de parâmetro não foram definidas, as propriedades dwStatus no DBPROPSET do conjunto de propriedades SSPARAMPROPS retornarão com DBSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="b4557-122">If the call to `ISSCommandWithParameters::SetParameterProperties` contains some parameters where the parameter info has been set, and some parameters where the parameter info has not been set, the dwStatus properties in the DBPROPSET of the SSPARAMPROPS property set will return with DBSTATUS_NOTSET.</span></span>  
  
 <span data-ttu-id="b4557-123">A estrutura SSPARAMPROPS é definida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b4557-123">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
 <span data-ttu-id="b4557-124">Aprimoramentos no mecanismo de banco de dados desde o [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permitem que ISSCommandWithParameters::SetParameterProperties obtenha descrições mais precisas dos resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="b4557-124">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ISSCommandWithParameters::SetParameterProperties to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="b4557-125">Esses resultados mais precisos podem ser diferentes dos valores retornados por ISSCommandWithParameters::SetParameterProperties em versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4557-125">These more accurate results may differ from the values returned by ISSCommandWithParameters::SetParameterProperties in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b4557-126">Para obter mais informações, veja [Descoberta de metadados](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="b4557-126">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
|<span data-ttu-id="b4557-127">Membro</span><span class="sxs-lookup"><span data-stu-id="b4557-127">Member</span></span>|<span data-ttu-id="b4557-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="b4557-128">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b4557-129">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="b4557-129">*iOrdinal*</span></span>|<span data-ttu-id="b4557-130">O ordinal do parâmetro passado.</span><span class="sxs-lookup"><span data-stu-id="b4557-130">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="b4557-131">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="b4557-131">*cPropertySets*</span></span>|<span data-ttu-id="b4557-132">O número de estruturas DBPROPSET em *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="b4557-132">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="b4557-133">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="b4557-133">*rgPropertySets*</span></span>|<span data-ttu-id="b4557-134">Um ponteiro para a memória no qual uma matriz de estruturas DBPROPSET deve ser retornada.</span><span class="sxs-lookup"><span data-stu-id="b4557-134">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4557-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b4557-135">See Also</span></span>  
 [<span data-ttu-id="b4557-136">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4557-136">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
