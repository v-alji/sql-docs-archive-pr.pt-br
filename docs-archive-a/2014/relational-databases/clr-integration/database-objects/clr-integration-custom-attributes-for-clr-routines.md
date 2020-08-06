---
title: Atributos personalizados para rotinas CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- SqlFacet attribute
- SqlTrigger attribute
- SqlProcedure attribute
- custom attributes [CLR integration]
- SqlUserDefinedAggregate attribute
- attributes [CLR integration]
- SqlMethod attribute
- SqlFunction attribute
- common language runtime [SQL Server], attributes
- SqlUserDefinedTypeAttribute attribute
ms.assetid: 95069d22-b05d-4670-b053-15ee2a664e33
author: rothja
ms.author: jroth
ms.openlocfilehash: 058bbec7f0f1f63fbd96258a0abe7a6c3d543d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568639"
---
# <a name="custom-attributes-for-clr-routines"></a><span data-ttu-id="38fad-102">Atributos personalizados para rotinas de CLR</span><span class="sxs-lookup"><span data-stu-id="38fad-102">Custom Attributes for CLR Routines</span></span>
  <span data-ttu-id="38fad-103">Os atributos listados podem ser aplicados a rotinas de Common Language Runtime (CLR), tipos definidos pelo usuário e agregações definidas pelo usuário que são registradas no [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38fad-103">The attributes listed can be applied to common language runtime (CLR) routines, user-defined types, and user-defined aggregates that are registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="38fad-104">Se o atributo não for aplicado, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assumirá o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="38fad-104">If the attribute is not applied, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assumes the default value.</span></span> <span data-ttu-id="38fad-105">Os atributos listados são definidos no namespace `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="38fad-105">The attributes listed are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="the-sqluserdefinedaggregate-attribute"></a><span data-ttu-id="38fad-106">O atributo SqlUserDefinedAggregate</span><span class="sxs-lookup"><span data-stu-id="38fad-106">The SqlUserDefinedAggregate Attribute</span></span>  
 <span data-ttu-id="38fad-107">O atributo `SqlUserDefinedAggregate` indica que o método deve ser registrado como uma agregação definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="38fad-107">The `SqlUserDefinedAggregate` attribute indicates that the method should be registered as a user-defined aggregate.</span></span> <span data-ttu-id="38fad-108">Todas as agregações definidas pelo usuário devem ser anotadas com esse atributo.</span><span class="sxs-lookup"><span data-stu-id="38fad-108">Every user-defined aggregate must be annotated with this attribute.</span></span>  
  
 <span data-ttu-id="38fad-109">Para obter mais informações, consulte [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span><span class="sxs-lookup"><span data-stu-id="38fad-109">For more information, see [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span></span>  
  
## <a name="the-sqlfunction-attribute"></a><span data-ttu-id="38fad-110">O atributo SqlFunction</span><span class="sxs-lookup"><span data-stu-id="38fad-110">The SqlFunction Attribute</span></span>  
 <span data-ttu-id="38fad-111">O atributo `SqlFunction` indica que o método deve ser registrado como uma função, com o conjunto apropriado de atributos de função.</span><span class="sxs-lookup"><span data-stu-id="38fad-111">The `SqlFunction` attribute indicates the method should be registered as a function, with the appropriate function attributes set.</span></span>  
  
 <span data-ttu-id="38fad-112">Para obter mais informações, consulte [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span><span class="sxs-lookup"><span data-stu-id="38fad-112">For more information, see [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span></span>  
  
## <a name="the-sqlfacet-attribute"></a><span data-ttu-id="38fad-113">O atributo SqlFacet</span><span class="sxs-lookup"><span data-stu-id="38fad-113">The SqlFacet Attribute</span></span>  
 <span data-ttu-id="38fad-114">O atributo `SqlFacet` é usado para retornar informações sobre o tipo de retorno de uma expressão UDT (tipo definido pelo usuário).</span><span class="sxs-lookup"><span data-stu-id="38fad-114">The `SqlFacet` attribute is used to return information about the return type of a user-defined type (UDT) expression.</span></span>  
  
 <span data-ttu-id="38fad-115">Para obter mais informações, consulte [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span><span class="sxs-lookup"><span data-stu-id="38fad-115">For more information, see [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span></span>  
  
## <a name="the-sqlprocedure-attribute"></a><span data-ttu-id="38fad-116">O atributo SqlProcedure</span><span class="sxs-lookup"><span data-stu-id="38fad-116">The SqlProcedure Attribute</span></span>  
 <span data-ttu-id="38fad-117">O atributo `SqlProcedure` indica o método que deve ser registrado como um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="38fad-117">The `SqlProcedure` attribute indicates the method should be registered as a stored procedure.</span></span> <span data-ttu-id="38fad-118">Esse atributo só é usado pelo Visual Studio para registrar o método especificado como um procedimento armazenado automaticamente; não é usado pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38fad-118">This attribute is used only by Visual Studio to register the specified method as a stored procedure automatically; it is not used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="38fad-119">Para obter mais informações, consulte [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span><span class="sxs-lookup"><span data-stu-id="38fad-119">For more information, see [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span></span>  
  
## <a name="the-sqltrigger-attribute"></a><span data-ttu-id="38fad-120">O atributo SqlTrigger</span><span class="sxs-lookup"><span data-stu-id="38fad-120">The SqlTrigger Attribute</span></span>  
 <span data-ttu-id="38fad-121">O atributo `SqlTrigger` indica que o método deve ser registrado como um gatilho.</span><span class="sxs-lookup"><span data-stu-id="38fad-121">The `SqlTrigger` attribute indicates the method should be registered as a trigger.</span></span>  
  
 <span data-ttu-id="38fad-122">Para obter mais informações, consulte [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) e [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span><span class="sxs-lookup"><span data-stu-id="38fad-122">For more information, see [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) and [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span></span>  
  
## <a name="the-sqluserdefinedtypeattribute"></a><span data-ttu-id="38fad-123">O SqlUserDefinedTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="38fad-123">The SqlUserDefinedTypeAttribute</span></span>  
 <span data-ttu-id="38fad-124">Você pode aplicar o SqlUserDefinedTypeAttribute a uma definição de classe no assembly.</span><span class="sxs-lookup"><span data-stu-id="38fad-124">You can apply the SqlUserDefinedTypeAttribute to a class definition in the assembly.</span></span> <span data-ttu-id="38fad-125">Ele faz com que o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] crie um tipo definido pelo usuário que é associado à definição de classe que tem esse atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="38fad-125">It causes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to create a user-defined type that is bound to the class definition which has this custom attribute.</span></span>  
  
 <span data-ttu-id="38fad-126">Para obter mais informações, consulte [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span><span class="sxs-lookup"><span data-stu-id="38fad-126">For more information, see [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span></span>  
  
## <a name="the-sqlmethod-attribute"></a><span data-ttu-id="38fad-127">O atributo SqlMethod</span><span class="sxs-lookup"><span data-stu-id="38fad-127">The SqlMethod Attribute</span></span>  
 <span data-ttu-id="38fad-128">O atributo `SqlMethod` é usado para indicar as propriedades de determinismo e acesso a dados de um método ou de uma propriedade em um UDT.</span><span class="sxs-lookup"><span data-stu-id="38fad-128">The `SqlMethod` attribute is used to indicate the determinism and data access properties of a method or a property on a UDT.</span></span>  
  
 <span data-ttu-id="38fad-129">Para obter mais informações, consulte [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span><span class="sxs-lookup"><span data-stu-id="38fad-129">For more information, see [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fad-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="38fad-130">See Also</span></span>  
 <span data-ttu-id="38fad-131">[Agregações CLR definidas pelo usuário](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span><span class="sxs-lookup"><span data-stu-id="38fad-131">[CLR User-Defined Aggregates](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span></span>  
 <span data-ttu-id="38fad-132">[Funções CLR definidas pelo usuário](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="38fad-132">[CLR User-Defined Functions](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="38fad-133">[Tipos definidos pelo usuário de CLR](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="38fad-133">[CLR User-Defined Types](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 <span data-ttu-id="38fad-134">[Procedimentos armazenados CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="38fad-134">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="38fad-135">Gatilhos de CLR</span><span class="sxs-lookup"><span data-stu-id="38fad-135">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
  
  
