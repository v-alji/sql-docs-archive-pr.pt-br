---
title: Criar um provedor de logs personalizado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom log providers [Integration Services], creating
ms.assetid: fc20af96-9eb8-4195-8d3f-8a4d7c753f24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1efb736aece2cc8d118c81326989559f0d17a60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680986"
---
# <a name="creating-a-custom-log-provider"></a><span data-ttu-id="33697-102">Criando um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="33697-102">Creating a Custom Log Provider</span></span>
  <span data-ttu-id="33697-103">O ambiente de tempo de execução do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] tem extensas capacidades de log.</span><span class="sxs-lookup"><span data-stu-id="33697-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time environment has extensive logging capabilities.</span></span> <span data-ttu-id="33697-104">Um log permite capturar eventos que ocorrem durante a execução de pacotes.</span><span class="sxs-lookup"><span data-stu-id="33697-104">A log lets you capture events that occur during package execution.</span></span> <span data-ttu-id="33697-105">O [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] inclui vários provedores de log que permitem a criação e o armazenamento de logs em vários formatos, como XML, texto, banco de dados ou no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="33697-105">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of log providers that enable logs to be created and stored in multiple formats, such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="33697-106">Se um desses provedores ou formatos de saída não forem adequados às suas necessidades, você pode criar um provedor de log personalizado.</span><span class="sxs-lookup"><span data-stu-id="33697-106">If one of these providers or output formats does not fit your needs, you can create a custom log provider.</span></span>

 <span data-ttu-id="33697-107">As etapas envolvidas na criação de um provedor de log personalizado são semelhantes às etapas de criação de qualquer outro objeto personalizado para o [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="33697-107">The steps involved in creating a custom log provider are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>

-   <span data-ttu-id="33697-108">Crie uma classe nova herdada da classe base.</span><span class="sxs-lookup"><span data-stu-id="33697-108">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="33697-109">Para um provedor de log, a classe base é <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>.</span><span class="sxs-lookup"><span data-stu-id="33697-109">For a log provider, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>.</span></span>

-   <span data-ttu-id="33697-110">Aplique o atributo que identifica o tipo de objeto para a classe.</span><span class="sxs-lookup"><span data-stu-id="33697-110">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="33697-111">Para um provedor de log, o atributo é <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="33697-111">For a log provider, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute>.</span></span>

-   <span data-ttu-id="33697-112">Substitua a implementação dos métodos e propriedades da classe base.</span><span class="sxs-lookup"><span data-stu-id="33697-112">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="33697-113">Para um provedor de log, eles incluem a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> e os métodos <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="33697-113">For a log provider, these include the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods.</span></span>

-   <span data-ttu-id="33697-114">As interfaces do usuário personalizadas para provedores de log personalizados não são implementadas no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33697-114">Custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="getting-started-with-a-custom-log-provider"></a><span data-ttu-id="33697-115">Guia de Introdução com um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="33697-115">Getting Started with a Custom Log Provider</span></span>

### <a name="creating-projects-and-classes"></a><span data-ttu-id="33697-116">Criando projetos e classes</span><span class="sxs-lookup"><span data-stu-id="33697-116">Creating Projects and Classes</span></span>
 <span data-ttu-id="33697-117">Como todos os provedores de log gerenciados derivam da classe base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, o primeiro passo para criar um provedor de log personalizado é criar um projeto de biblioteca de classes na linguagem de programação gerenciada de sua preferência e criar uma classe herdada da classe base.</span><span class="sxs-lookup"><span data-stu-id="33697-117">Because all managed log providers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, the first step when you create a custom log provider is to create a class library project in your preferred managed programming language, and then create a class that inherits from the base class.</span></span> <span data-ttu-id="33697-118">Nessa classe derivada, você substituirá os métodos e propriedades da classe base para implementar sua funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="33697-118">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>

 <span data-ttu-id="33697-119">Configure o projeto para assinar o assembly que será gerado com um arquivo de chave de nome forte.</span><span class="sxs-lookup"><span data-stu-id="33697-119">Configure the project to sign the assembly that will be generated with a strong name key file.</span></span>

> [!NOTE]
>  <span data-ttu-id="33697-120">Muitos provedores de log do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] têm uma interface do usuário personalizada que implementa o <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> e substitui a caixa de texto **Configuração** na caixa de diálogo **Configurar Logs de SSIS** por uma lista suspensa filtrada com gerenciadores de conexões disponíveis.</span><span class="sxs-lookup"><span data-stu-id="33697-120">Many [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] log providers have a custom user interface that implements <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI> and replaces the **Configuration** text box in the **Configure SSIS Logs** dialog box with a filtered dropdown list of available connection managers.</span></span> <span data-ttu-id="33697-121">Porém, interfaces do usuário personalizadas para provedores de log personalizados não são implementadas no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33697-121">However custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

### <a name="applying-the-dtslogprovider-attribute"></a><span data-ttu-id="33697-122">Aplicando o atributo DtsLogProvider</span><span class="sxs-lookup"><span data-stu-id="33697-122">Applying the DtsLogProvider Attribute</span></span>
 <span data-ttu-id="33697-123">Aplique o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> à classe que você criou para identificá-lo como um provedor de log.</span><span class="sxs-lookup"><span data-stu-id="33697-123">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class that you have created to identify it as a log provider.</span></span> <span data-ttu-id="33697-124">Esse atributo fornece informações de tempo de design, como o nome e a descrição do provedor de log.</span><span class="sxs-lookup"><span data-stu-id="33697-124">This attribute provides design-time information such as the name and description of the log provider.</span></span> <span data-ttu-id="33697-125">As `DisplayName` `Description` Propriedades e do atributo correspondem ao **nome** e às `Description` colunas exibidas no editor **Configurar Logs do SSIS** , que é exibido ao configurar o registro em log para um pacote no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33697-125">The `DisplayName` and `Description` properties of the attribute correspond to the **Name** and `Description` columns displayed in the **Configure SSIS Logs** editor, which is displayed when configuring logging for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="33697-126">A propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.LogProviderType%2A> do atributo não é usada.</span><span class="sxs-lookup"><span data-stu-id="33697-126">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.LogProviderType%2A> property of the attribute is not used.</span></span> <span data-ttu-id="33697-127">Porém, você deve digitar um valor para ela ou o provedor de log personalizado não aparecerá na lista de provedores de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="33697-127">However, you must enter a value for it, or the custom log provider will not appear in the list of available log providers.</span></span>

> [!NOTE]
>  <span data-ttu-id="33697-128">Como as interfaces do usuário personalizadas para provedores de log personalizados não são implementadas no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], especificar um valor para a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.UITypeName%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="33697-128">Since custom user interfaces for custom log providers are not implemented in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], specifying a value for the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> has no effect.</span></span>

```vb
<DtsLogProvider(DisplayName:="MyLogProvider", Description:="A simple log provider.", LogProviderType:="Custom")> _
Public Class MyLogProvider
     Inherits LogProviderBase
    ' TODO: Override the base class methods.
End Class
```

```csharp
[DtsLogProvider(DisplayName="MyLogProvider", Description="A simple log provider.", LogProviderType="Custom")]
public class MyLogProvider : LogProviderBase
{
    // TODO: Override the base class methods.
}
```

## <a name="building-deploying-and-debugging-a-custom-log-provider"></a><span data-ttu-id="33697-129">Compilando, implantando e depurando um provedor de log personalizado</span><span class="sxs-lookup"><span data-stu-id="33697-129">Building, Deploying, and Debugging a Custom Log Provider</span></span>
 <span data-ttu-id="33697-130">As etapas para compilar, implantar e depurar um provedor de log personalizado no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] são muito semelhantes às etapas necessárias para outros tipos de objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="33697-130">The steps for building, deploying, and debugging a custom log provider in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="33697-131">Para obter mais informações, consulte [Compilar, implantar e depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="33697-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>

<span data-ttu-id="33697-132">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="33697-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="33697-133">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="33697-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="33697-134">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="33697-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="33697-135">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="33697-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="33697-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="33697-136">See Also</span></span>
 <span data-ttu-id="33697-137">[Codificando um provedor de log personalizado](coding-a-custom-log-provider.md) [desenvolvendo uma interface do usuário para um provedor de log personalizado](developing-a-user-interface-for-a-custom-log-provider.md)</span><span class="sxs-lookup"><span data-stu-id="33697-137">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md)</span></span>


