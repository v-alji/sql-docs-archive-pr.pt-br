---
title: Configurar o acesso na memória ou DirectQuery para um banco de dados modelo de tabela | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5d439a9-5be1-4145-90e8-90777d80e98b
author: minewiskan
ms.author: owend
ms.openlocfilehash: a607bc6c11f35736487932bdf10d239afc8b5355
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679036"
---
# <a name="configure-in-memory-or-directquery-access-for-a-tabular-model-database"></a><span data-ttu-id="5c381-102">Configure o Acesso Na Memória ou DirectQuery para um banco de dados modelo de tabela</span><span class="sxs-lookup"><span data-stu-id="5c381-102">Configure In-Memory or DirectQuery Access for a Tabular Model Database</span></span>
  <span data-ttu-id="5c381-103">Este tópico descreve como alterar as propriedades de conexão de um modelo de tabela que já foi implantado, para habilitar o uso do modelo no modo Consulta Direta.</span><span class="sxs-lookup"><span data-stu-id="5c381-103">This topic describes how to change the connection properties of a tabular model that has already been deployed, to enable use of the model in Direct Query mode.</span></span>  
  
 <span data-ttu-id="5c381-104">Para obter mais informações sobre essas propriedades e a configuração para os cenários mais comuns, consulte [cenários de implantação do DirectQuery &#40;SSAS tabular&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="5c381-104">For more information about these properties, and configuration for the most common scenarios, see [DirectQuery Deployment Scenarios &#40;SSAS Tabular&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c381-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c381-105">Requirements</span></span>  
 <span data-ttu-id="5c381-106">Habilitar o uso do modo Consulta Direta em um modelo de tabela é um processo de várias etapas.</span><span class="sxs-lookup"><span data-stu-id="5c381-106">Enabling the use of Direct Query mode on a tabular model is a multistep process.</span></span> <span data-ttu-id="5c381-107">Você deve:</span><span class="sxs-lookup"><span data-stu-id="5c381-107">You must:</span></span>  
  
1.  <span data-ttu-id="5c381-108">Verificar se o modelo não tem recursos que podem causar erros de validação no modo Consulta Direta.</span><span class="sxs-lookup"><span data-stu-id="5c381-108">Ensure that the model does not have features which might cause validation errors in Direct Query mode.</span></span>  
  
2.  <span data-ttu-id="5c381-109">Alterar o modo de armazenamento no modelo para dar suporte a Consulta Direta.</span><span class="sxs-lookup"><span data-stu-id="5c381-109">Change the storage mode on the model to support Direct Query.</span></span>  
  
3.  <span data-ttu-id="5c381-110">Implantar o modelo em um modo que dá suporte a consultas em um modo Consulta Direta híbrido ou puro.</span><span class="sxs-lookup"><span data-stu-id="5c381-110">Deploy the model in a mode that supports queries in either a hybrid or pure Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="5c381-111">Editar a cadeia de conexão no banco de dados implantado para dar suporte ao modo Consulta Direta.</span><span class="sxs-lookup"><span data-stu-id="5c381-111">Edit the connection string on the deployed database to support Direct Query mode.</span></span>  
  
 <span data-ttu-id="5c381-112">Este tópico supõe que você tenha criado e validado seu modelo, e somente precise habilitar o acesso Consulta Direta de um cliente como o [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c381-112">This topic assumes that you have created and validated your model, and only need to enable Direct Query access from a client such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="5c381-113">Procedimento</span><span class="sxs-lookup"><span data-stu-id="5c381-113">Procedure</span></span>  
  
#### <a name="change-the-connection-string-properties-of-the-model"></a><span data-ttu-id="5c381-114">Alterar as propriedades de cadeia de conexão de um modelo</span><span class="sxs-lookup"><span data-stu-id="5c381-114">Change the Connection String Properties of the Model</span></span>  
  
1.  <span data-ttu-id="5c381-115">No SQL Server Management Studio, abra a instância para a qual você implantou o modelo.</span><span class="sxs-lookup"><span data-stu-id="5c381-115">In SQL Server Management Studio, open the instance to which you deployed the model.</span></span>  
  
2.  <span data-ttu-id="5c381-116">No Pesquisador de objetos, clique com o botão direito do mouse no nome do banco de dados modelo e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5c381-116">In Object Explorer, right-click the name of the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="5c381-117">Localize a propriedade **DirectQueryMode**.</span><span class="sxs-lookup"><span data-stu-id="5c381-117">Locate the property, **DirectQueryMode**.</span></span> <span data-ttu-id="5c381-118">Para habilitar o uso da fonte de dados relacional, esta propriedade deve ser definida como um destes valores:</span><span class="sxs-lookup"><span data-stu-id="5c381-118">To enable use of the relational data source, this property must be set to one of these values:</span></span>  
  
    -   <span data-ttu-id="5c381-119">**DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="5c381-119">**DirectQuery**</span></span>  
  
    -   <span data-ttu-id="5c381-120">**InMemoryWithDirectQuery**</span><span class="sxs-lookup"><span data-stu-id="5c381-120">**InMemoryWithDirectQuery**</span></span>  
  
    -   <span data-ttu-id="5c381-121">**DirectQueryWithInMemory**</span><span class="sxs-lookup"><span data-stu-id="5c381-121">**DirectQueryWithInMemory**</span></span>  
  
  
