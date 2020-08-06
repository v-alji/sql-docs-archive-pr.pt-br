---
title: Informações sobre representação | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42319d60-ccd0-46b8-af0b-f0968c390d8a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f9226fdbe8656aecf0f9173976c67ee386040d6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679078"
---
# <a name="impersonation-information"></a><span data-ttu-id="73726-102">Informações sobre representação</span><span class="sxs-lookup"><span data-stu-id="73726-102">Impersonation Information</span></span>
  <span data-ttu-id="73726-103">Use a página **Informações sobre Representação** para especificar as credenciais que o Analysis Services usará para se conectar à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="73726-103">Use the **Impersonation Information** page to specify the credentials that Analysis Services will use to connect to the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="73726-104">Opções</span><span class="sxs-lookup"><span data-stu-id="73726-104">Options</span></span>  
 <span data-ttu-id="73726-105">**Usar nome de usuário e senha específicos do Windows**</span><span class="sxs-lookup"><span data-stu-id="73726-105">**Use a specific Windows user name and password**</span></span>  
 <span data-ttu-id="73726-106">Selecione esta opção para fazer com que o objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] use as credenciais de segurança de uma conta de usuário do Windows especificada.</span><span class="sxs-lookup"><span data-stu-id="73726-106">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of a specified Windows user account.</span></span> <span data-ttu-id="73726-107">As credenciais especificadas são usadas para processamento, consultas ROLAP, associações fora de linha, cubos locais, modelos de mineração, partições remotas, objetos vinculados e sincronização do destino para a origem.</span><span class="sxs-lookup"><span data-stu-id="73726-107">The specified credentials will be used for processing, ROLAP queries, out-of-line bindings, local cubes, mining models, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="73726-108">No entanto, para instruções OPENQUERY de extensões DMX, essa opção é ignorada e as credenciais do usuário atual serão usadas.</span><span class="sxs-lookup"><span data-stu-id="73726-108">However, for Data Mining Extensions (DMX) OPENQUERY statements, this option is ignored and the credentials of the current user will be used.</span></span>  
  
 <span data-ttu-id="73726-109">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="73726-109">**User name**</span></span>  
 <span data-ttu-id="73726-110">Digite o domínio e o nome da conta de usuário a serem usados pelo objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selecionado.</span><span class="sxs-lookup"><span data-stu-id="73726-110">Type the domain and name of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="73726-111">Use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="73726-111">Use the following format:</span></span>  
  
 <span data-ttu-id="73726-112">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="73726-112">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="73726-113">Essa opção estará habilitada apenas se a opção **Usar um nome e uma senha específicos** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="73726-113">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="73726-114">**Senha**</span><span class="sxs-lookup"><span data-stu-id="73726-114">**Password**</span></span>  
 <span data-ttu-id="73726-115">Digite a senha da conta de usuário a ser usada pelo objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selecionado.</span><span class="sxs-lookup"><span data-stu-id="73726-115">Type the password of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="73726-116">Essa opção estará habilitada apenas se a opção **Usar um nome e uma senha específicos** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="73726-116">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="73726-117">**Usar a conta de serviço**</span><span class="sxs-lookup"><span data-stu-id="73726-117">**Use the service account**</span></span>  
 <span data-ttu-id="73726-118">Selecione esta opção para fazer o objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usar as credenciais de segurança associadas ao serviço do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que gerencia o objeto.</span><span class="sxs-lookup"><span data-stu-id="73726-118">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the object.</span></span> <span data-ttu-id="73726-119">As credenciais da conta de serviço são usadas para processamento, consultas ROLAP, partições remotas, objetos vinculados e sincronização do destino para a origem.</span><span class="sxs-lookup"><span data-stu-id="73726-119">The service account credentials will be used for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="73726-120">No entanto, para instruções OPENQUERY do Data Mining Extensions (DMX), cubos locais e modelos de mineração, as credenciais do usuário atual são usadas.</span><span class="sxs-lookup"><span data-stu-id="73726-120">However, for Data Mining Extensions (DMX) OPENQUERY statements, local cubes, and mining models, the credentials of the current user will be used.</span></span> <span data-ttu-id="73726-121">Essa opção não tem suporte para associações fora de linha.</span><span class="sxs-lookup"><span data-stu-id="73726-121">This option is not supported for out-of-line bindings.</span></span>  
  
 <span data-ttu-id="73726-122">**Usar as credenciais do usuário atual**</span><span class="sxs-lookup"><span data-stu-id="73726-122">**Use the credentials of the current user**</span></span>  
 <span data-ttu-id="73726-123">Selecione esta opção para fazer com que o objeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] use as credenciais de segurança do usuário atual para associações fora de linha, OPENQUERY DMX, cubos locais e modelos de mineração.</span><span class="sxs-lookup"><span data-stu-id="73726-123">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of the current user for out-of-line bindings, DMX OPENQUERY, local cubes, and mining models.</span></span> <span data-ttu-id="73726-124">A opção não tem suporte para processamento, consultas ROLAP, partições remotas, objetos vinculados e sincronização do destino para a origem.</span><span class="sxs-lookup"><span data-stu-id="73726-124">This option is not supported for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span>  
  
 <span data-ttu-id="73726-125">**Herd**</span><span class="sxs-lookup"><span data-stu-id="73726-125">**Inherit**</span></span>  
 <span data-ttu-id="73726-126">Selecione esta opção para usar o comportamento de representação, definido no nível de banco de dados que foi definido pelo administrador do servidor usando a propriedade `DataSourceImpersonation` do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="73726-126">Select this option to use the impersonation behavior, defined at the database level, which has been set by the server administrator using the `DataSourceImpersonation` database property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73726-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="73726-127">See Also</span></span>  
 <span data-ttu-id="73726-128">[Fontes de dados em modelos multidimensionais](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="73726-128">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="73726-129">Fontes de dados com suporte &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="73726-129">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
