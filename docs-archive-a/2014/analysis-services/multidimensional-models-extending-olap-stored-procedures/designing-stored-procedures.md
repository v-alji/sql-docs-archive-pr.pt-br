---
title: Criando procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services], designing
- dependent assemblies [Analysis Services]
- assemblies [Analysis Services]
ms.assetid: af4e7bd5-041b-4a40-9942-0ef6a3af46c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 42b33873d6bdf28f7f702bcf186d681f57d6024d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680696"
---
# <a name="designing-stored-procedures"></a><span data-ttu-id="ee36f-102">Projetando procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ee36f-102">Designing Stored Procedures</span></span>
  <span data-ttu-id="ee36f-103">Tanto o Analysis Management Objects (AMO) do modelo de objeto administrativo como o [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® Data Objects (Multidimensional) (ADO MD) do modelo de objeto orientado a cliente estão disponíveis nos procedimentos armazenados.</span><span class="sxs-lookup"><span data-stu-id="ee36f-103">Both the administrative object model Analysis Management Objects (AMO) and the client oriented object model [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX® Data Objects (Multidimensional) (ADO MD) are available in stored procedures.</span></span>  
  
 <span data-ttu-id="ee36f-104">Os procedimentos armazenados devem estar no escopo (do servidor ou do banco de dados) para serem visíveis no nível da linguagem MDX que serão chamadas.</span><span class="sxs-lookup"><span data-stu-id="ee36f-104">Stored procedures must be in scope (either the server or the database) to be visible at the Multidimensional Expressions (MDX) level to be called.</span></span> <span data-ttu-id="ee36f-105">No entanto, uma vez um chamado o procedimento armazenado, seu escopo não fica limitado a ações sob seu pai.</span><span class="sxs-lookup"><span data-stu-id="ee36f-105">However, once a stored procedure is invoked, its scope is not limited to actions under its parent.</span></span> <span data-ttu-id="ee36f-106">Um procedimento armazenado pode fazer alterações ou modificações em qualquer lugar do servidor, sujeito apenas às limitações de segurança do processo do usuário que o chama ou às limitações da transação em que está operando.</span><span class="sxs-lookup"><span data-stu-id="ee36f-106">A stored procedure may make changes or modifications anywhere on the server, subject only to the security limitations of the user process that invokes it or to the limitations of the transaction in which it is operating.</span></span>  
  
 <span data-ttu-id="ee36f-107">Procedimentos de escopo de servidor ficam disponíveis em todos os contextos no servidor.</span><span class="sxs-lookup"><span data-stu-id="ee36f-107">Server scope procedures are available in all contexts on the server.</span></span> <span data-ttu-id="ee36f-108">Procedimentos armazenados de escopo de banco de dados ficam visíveis apenas no contexto do banco de dados no qual foram definidos.</span><span class="sxs-lookup"><span data-stu-id="ee36f-108">Database scope stored procedures are visible only in the database context of the database in which they are defined.</span></span>  
  
 <span data-ttu-id="ee36f-109">Como toda função MDX, o procedimento armazenado deve ser resolvido antes que a sessão MDX possa prosseguir; os procedimentos armazenados bloqueiam as sessões MDX durante sua execução.</span><span class="sxs-lookup"><span data-stu-id="ee36f-109">As with any MDX function, stored procedure must be resolved before an MDX session can continue; stored procedures lock MDX sessions while executing.</span></span> <span data-ttu-id="ee36f-110">A menos que exista um motivo específico para parar uma sessão MDX à espera de uma interação do usuário, qualquer interação do usuário (como caixas de diálogo) não são aconselhadas.</span><span class="sxs-lookup"><span data-stu-id="ee36f-110">Unless a specific reason exists to halt an MDX session pending user interaction, then user interactions (such as dialog boxes) are discouraged.</span></span>  
  
## <a name="dependent-assemblies"></a><span data-ttu-id="ee36f-111">Assemblies dependentes</span><span class="sxs-lookup"><span data-stu-id="ee36f-111">Dependent Assemblies</span></span>  
 <span data-ttu-id="ee36f-112">Todos os assemblies dependentes devem ser carregados em uma instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para serem localizados pelo CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="ee36f-112">All dependent assemblies must be loaded into an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to be found by the common language runtime (CLR).</span></span> <span data-ttu-id="ee36f-113">O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] armazena os assemblies dependentes na mesma pasta do assembly principal, de modo que o CLR resolve automaticamente todas as referências das funções para as funções desses assemblies.</span><span class="sxs-lookup"><span data-stu-id="ee36f-113">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stores the dependent assemblies in the same folder as the main assembly, so the CLR automatically resolves all function references to functions in those assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee36f-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ee36f-114">See Also</span></span>  
 <span data-ttu-id="ee36f-115">[Gerenciamento de assemblies de modelo multidimensional](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="ee36f-115">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="ee36f-116">Definindo procedimentos armazenados</span><span class="sxs-lookup"><span data-stu-id="ee36f-116">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
