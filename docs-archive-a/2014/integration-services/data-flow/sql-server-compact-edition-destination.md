---
title: Destino do SQL Server Compact Edition | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlservercompactdest.f1
helpviewer_keywords:
- destinations [Integration Services], SQL Server Compact
- SQL Server Compact, destination
- inserting data
ms.assetid: 697742ba-cc14-414d-8187-1845ad0dd99b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfeb0bfce54c9ebefb5c526656be6b736dc0d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582058"
---
# <a name="sql-server-compact-edition-destination"></a><span data-ttu-id="eaf1f-102">Destino do SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="eaf1f-102">SQL Server Compact Edition Destination</span></span>
  <span data-ttu-id="eaf1f-103">O destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact grava dados em bancos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination writes data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact databases.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eaf1f-104">Em um computador de 64 bits, você deve executar pacotes que se conectam a fontes de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact no modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-104">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="eaf1f-105">O provedor do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, que o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa para se conectar a fontes de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, só está disponível na versão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
 <span data-ttu-id="eaf1f-106">Você configura o destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact especificando o nome da tabela na qual o destino [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact deve inserir os dados.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-106">You configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination by specifying the name of the table into which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination inserts the data.</span></span> <span data-ttu-id="eaf1f-107">A propriedade personalizada TableName do destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact contém o nome da tabela.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-107">The custom property TableName of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination contains the table name.</span></span>  
  
 <span data-ttu-id="eaf1f-108">Esse destino usa um gerenciador de conexões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact para conectar-se a uma fonte de dados, e o gerenciador de conexões especifica o provedor OLE DB a ser usado.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-108">This destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="eaf1f-109">Para obter mais informações, consulte [Gerenciador de Conexões do SQL Server Compact Edition](../connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="eaf1f-109">For more information, see [SQL Server Compact Edition Connection Manager](../connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
 <span data-ttu-id="eaf1f-110">O destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact inclui a propriedade personalizada TableName, que pode ser atualizada por uma expressão de propriedade quando o pacote é carregado.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination includes the TableName custom property, which can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="eaf1f-111">Para obter mais informações, consulte [Integration Services &#40;SSIS&#41; Expressões](../expressions/integration-services-ssis-expressions.md), [Usar expressões de propriedade em pacotes](../expressions/use-property-expressions-in-packages.md) e [Propriedades personalizadas de destino do SQL Server Compact Edition](sql-server-compact-edition-destination-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="eaf1f-111">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [SQL Server Compact Edition Destination Custom Properties](sql-server-compact-edition-destination-custom-properties.md).</span></span>  
  
 <span data-ttu-id="eaf1f-112">O destino do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact tem uma entrada e não aceita uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination has one input and does not support an error output.</span></span>  
  
## <a name="configuration-of-the-sql-server-compact-edition-destination"></a><span data-ttu-id="eaf1f-113">Configuração do destino do SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="eaf1f-113">Configuration of the SQL Server Compact Edition Destination</span></span>  
 <span data-ttu-id="eaf1f-114">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-114">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="eaf1f-115">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="eaf1f-115">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="eaf1f-116">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="eaf1f-116">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="eaf1f-117">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="eaf1f-117">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="eaf1f-118">Propriedades personalizadas do destino SQL Server</span><span class="sxs-lookup"><span data-stu-id="eaf1f-118">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="eaf1f-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="eaf1f-119">Related Tasks</span></span>  
 <span data-ttu-id="eaf1f-120">Para obter mais informações sobre como definir as propriedades desse componente, consulte [Definir as propriedades de um componente de fluxo de dados](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="eaf1f-120">For more information about how to set properties of this component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf1f-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eaf1f-121">See Also</span></span>  
 [<span data-ttu-id="eaf1f-122">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="eaf1f-122">Data Flow</span></span>](data-flow.md)  
  
  
