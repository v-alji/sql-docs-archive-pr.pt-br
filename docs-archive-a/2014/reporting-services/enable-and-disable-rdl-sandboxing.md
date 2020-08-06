---
title: Habilitar e desabilitar RDL Sandboxing | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d5619e9f-ec5b-4376-9b34-1f74de6fade7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7af1477751093862c99d00978278315e600511e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682143"
---
# <a name="enable-and-disable-rdl-sandboxing"></a><span data-ttu-id="0dee9-102">Habilitar e desabilitar o RDL Sandboxing</span><span class="sxs-lookup"><span data-stu-id="0dee9-102">Enable and Disable RDL Sandboxing</span></span>
  <span data-ttu-id="0dee9-103">O recurso RDL Sandboxing (Linguagem RDL) permite que você detecte e restrinja o uso de tipos específicos de recurso por locatários individuais em um ambiente de vários locatários que utilizam um único web farm de servidores de relatório.</span><span class="sxs-lookup"><span data-stu-id="0dee9-103">The RDL (Report Definition Language) Sandboxing feature lets you detect and restrict the usage of specific types of resources, by individual tenants, in an environment of multiple tenants that use a single web farm of report servers.</span></span> <span data-ttu-id="0dee9-104">Um exemplo disso é um cenário de serviços de hospedagem onde você poderia manter um único web farm de servidores de relatório que são usados por vários locatários e talvez empresas diferentes.</span><span class="sxs-lookup"><span data-stu-id="0dee9-104">An example of this is a hosting services scenario where you might maintain a single web farm of report servers that are used by multiple tenants, and perhaps different companies.</span></span> <span data-ttu-id="0dee9-105">Como administrador de servidor de relatório, você pode permitir que esse recurso ajude a obter os objetivos seguintes:</span><span class="sxs-lookup"><span data-stu-id="0dee9-105">As a report server administrator, you can enable this feature to help achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="0dee9-106">Restringir tamanhos de recursos externos.</span><span class="sxs-lookup"><span data-stu-id="0dee9-106">Restrict external resource sizes.</span></span> <span data-ttu-id="0dee9-107">Recursos externos incluem imagens, arquivos .xslt e dados de mapa.</span><span class="sxs-lookup"><span data-stu-id="0dee9-107">External resources include images, .xslt files, and map data.</span></span>  
  
-   <span data-ttu-id="0dee9-108">Na hora da publicação do relatório, tipos de limite e membros que são usados em texto de expressão.</span><span class="sxs-lookup"><span data-stu-id="0dee9-108">At report publish time, limit types and members that are used in expression text.</span></span>  
  
-   <span data-ttu-id="0dee9-109">Na hora do processamento do relatório, limite o comprimento do texto e o tamanho do valor de retorno para expressões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-109">At report processing time, limit the length of the text and the size of the return value for expressions.</span></span>  
  
 <span data-ttu-id="0dee9-110">Quando o RDL Sandboxing está habilitado, os seguintes recursos são desabilitados:</span><span class="sxs-lookup"><span data-stu-id="0dee9-110">When RDL Sandboxing is enabled, the following features are disabled:</span></span>  
  
-   <span data-ttu-id="0dee9-111">Código personalizado no **\<Code>** elemento de uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="0dee9-111">Custom code in the **\<Code>** element of a report definition.</span></span>  
  
-   <span data-ttu-id="0dee9-112">Modo de compatibilidade com versões anteriores do RDL para itens de relatório personalizados do [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0dee9-112">RDL backward compatibility mode for [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] custom report items.</span></span>  
  
-   <span data-ttu-id="0dee9-113">Parâmetros nomeados em expressões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-113">Named parameters in expressions.</span></span>  
  
 <span data-ttu-id="0dee9-114">Este tópico descreve cada elemento no elemento <`RDLSandboxing`> no arquivo RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="0dee9-114">This topic describes each element in the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span> <span data-ttu-id="0dee9-115">Para obter mais informações sobre como modificar esse arquivo, veja [Modificar um arquivo de configuração do Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="0dee9-115">For more information about how to modify this file, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="0dee9-116">Um log de rastreamento de servidor registra atividade relacionada ao recurso RDL Sandboxing.</span><span class="sxs-lookup"><span data-stu-id="0dee9-116">A server trace log records activity related to the RDL Sandboxing feature.</span></span> <span data-ttu-id="0dee9-117">Para obter mais informações sobre logs de rastreamento, consulte [Log de rastreamento do serviço Servidor de Relatório](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="0dee9-117">For more information about trace logs, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="0dee9-118">Exemplo de Configuração</span><span class="sxs-lookup"><span data-stu-id="0dee9-118">Example Configuration</span></span>  
 <span data-ttu-id="0dee9-119">O exemplo a seguir mostra as configurações e os valores de exemplo para o `RDLSandboxing` elemento <> no arquivo RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="0dee9-119">The following example shows the settings and example values for the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span>  
  
```  
<RDLSandboxing>  
   <MaxExpressionLength>5000</MaxExpressionLength>  
   <MaxResourceSize>5000</MaxResourceSize>  
   <MaxStringResultLength>3000</MaxStringResultLength>  
   <MaxArrayResultLength>250</MaxArrayResultLength>  
   <Types>  
      <Allow Namespace="System.Drawing" AllowNew="True">Bitmap</Allow>  
      <Allow Namespace="TypeConverters.Custom" AllowNew="True">*</Allow>  
   </Types>  
   <Members>  
      <Deny>Format</Deny>  
      <Deny>StrDup</Deny>  
   </Members>  
</RDLSandboxing>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="0dee9-120">Definições de configuração</span><span class="sxs-lookup"><span data-stu-id="0dee9-120">Configuration Settings</span></span>  
 <span data-ttu-id="0dee9-121">A tabela a seguir fornece informações sobre definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="0dee9-121">The following table provides information about configuration settings.</span></span> <span data-ttu-id="0dee9-122">As configurações são apresentadas na ordem em que aparecem no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="0dee9-122">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="0dee9-123">Configuração</span><span class="sxs-lookup"><span data-stu-id="0dee9-123">Setting</span></span>|<span data-ttu-id="0dee9-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="0dee9-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0dee9-125">**MaxExpressionLength**</span><span class="sxs-lookup"><span data-stu-id="0dee9-125">**MaxExpressionLength**</span></span>|<span data-ttu-id="0dee9-126">Número máximo de caracteres permitido em expressões RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-126">Maximum number of characters allowed in RDL expressions.</span></span><br /><br /> <span data-ttu-id="0dee9-127">Padrão: 1000</span><span class="sxs-lookup"><span data-stu-id="0dee9-127">Default: 1000</span></span>|  
|<span data-ttu-id="0dee9-128">**MaxResourceSize**</span><span class="sxs-lookup"><span data-stu-id="0dee9-128">**MaxResourceSize**</span></span>|<span data-ttu-id="0dee9-129">Número máximo de KB permitido em um recurso externo.</span><span class="sxs-lookup"><span data-stu-id="0dee9-129">Maximum number of KB allowed for an external resource.</span></span><br /><br /> <span data-ttu-id="0dee9-130">Padrão: 100</span><span class="sxs-lookup"><span data-stu-id="0dee9-130">Default: 100</span></span>|  
|<span data-ttu-id="0dee9-131">**MaxStringResultLength**</span><span class="sxs-lookup"><span data-stu-id="0dee9-131">**MaxStringResultLength**</span></span>|<span data-ttu-id="0dee9-132">Número máximo de caracteres permitido em um valor de retorno para uma expressão RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-132">Maximum number of characters allowed in a return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="0dee9-133">Padrão: 1000</span><span class="sxs-lookup"><span data-stu-id="0dee9-133">Default: 1000</span></span>|  
|<span data-ttu-id="0dee9-134">**MaxArrayResultLength**</span><span class="sxs-lookup"><span data-stu-id="0dee9-134">**MaxArrayResultLength**</span></span>|<span data-ttu-id="0dee9-135">Número máximo de itens permitido em um valor de resposta de matrizes para uma expressão RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-135">Maximum number of items allowed in an array return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="0dee9-136">Padrão: 100</span><span class="sxs-lookup"><span data-stu-id="0dee9-136">Default: 100</span></span>|  
|<span data-ttu-id="0dee9-137">**Types**</span><span class="sxs-lookup"><span data-stu-id="0dee9-137">**Types**</span></span>|<span data-ttu-id="0dee9-138">A lista de membros para permitir dentro de expressões RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-138">The list of members to allow within RDL expressions.</span></span>|  
|<span data-ttu-id="0dee9-139">**Permitir**</span><span class="sxs-lookup"><span data-stu-id="0dee9-139">**Allow**</span></span>|<span data-ttu-id="0dee9-140">Um tipo ou conjunto de tipos para permitir em expressões RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-140">A type or set of types to allow in RDL expressions.</span></span>|  
|<span data-ttu-id="0dee9-141">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="0dee9-141">**Namespace**</span></span>|<span data-ttu-id="0dee9-142">Atributo para **Allow** que é o namespace que contém um ou mais tipos que se aplicam a Valor.</span><span class="sxs-lookup"><span data-stu-id="0dee9-142">Attribute for **Allow** that is the namespace that contains one or more types that apply to Value.</span></span> <span data-ttu-id="0dee9-143">Esta propriedade não diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0dee9-143">This property is case-insensitive.</span></span>|  
|`AllowNew`|<span data-ttu-id="0dee9-144">Atributo booliano para **permitir** que controla se novas instâncias do tipo têm permissão para serem criadas em expressões RDL ou em um **\<Class>** elemento RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-144">Boolean attribute for **Allow** that controls whether new instances of the type are allowed to be created in RDL expressions or in an RDL **\<Class>** element.</span></span><br /><br /> <span data-ttu-id="0dee9-145">Observação: quando o `RDLSandboxing` está habilitado, novas matrizes não podem ser criadas em expressões RDL, independentemente da configuração de `AllowNew` .</span><span class="sxs-lookup"><span data-stu-id="0dee9-145">Note: When `RDLSandboxing` is enabled, new arrays cannot be created in RDL expressions, regardless of the setting of `AllowNew`.</span></span>|  
|<span data-ttu-id="0dee9-146">**Valor**</span><span class="sxs-lookup"><span data-stu-id="0dee9-146">**Value**</span></span>|<span data-ttu-id="0dee9-147">Valor para **Allow** que é o nome do tipo para permitir em expressões RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-147">Value for **Allow** that is the name of the type to allow in RDL expressions.</span></span> <span data-ttu-id="0dee9-148">O valor **\*** indica que todos os tipos no namespace são permitidos.</span><span class="sxs-lookup"><span data-stu-id="0dee9-148">The value **\*** indicates that all types in the namespace are allowed.</span></span> <span data-ttu-id="0dee9-149">Esta propriedade não diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0dee9-149">This property is case-insensitive.</span></span>|  
|<span data-ttu-id="0dee9-150">**Membros**</span><span class="sxs-lookup"><span data-stu-id="0dee9-150">**Members**</span></span>|<span data-ttu-id="0dee9-151">Para a lista de tipos que são incluídos no **\<Types>** elemento, a lista de nomes de membros que não são permitidos em expressões RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-151">For the list of types that are include in the **\<Types>** element, the list of member names that are not allowed in RDL expressions.</span></span>|  
|<span data-ttu-id="0dee9-152">**Deny**</span><span class="sxs-lookup"><span data-stu-id="0dee9-152">**Deny**</span></span>|<span data-ttu-id="0dee9-153">O nome de um membro que não é permitido em expressões RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-153">The name of a member that is not allowed in RDL expressions.</span></span> <span data-ttu-id="0dee9-154">Esta propriedade não diferencia maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0dee9-154">This property is case-insensitive.</span></span><br /><br /> <span data-ttu-id="0dee9-155">Observação: quando **Negar** é especificado para um membro, não é permitido usar todos os membros com esse nome para todos os tipos.</span><span class="sxs-lookup"><span data-stu-id="0dee9-155">Note: When **Deny** is specified for a member, all members with this name for all types are not allowed.</span></span>|  
  
## <a name="working-with-expressions-when-rdl-sandboxing-is-enabled"></a><span data-ttu-id="0dee9-156">Trabalhando com expressões quando o RDL Sandboxing está habilitado</span><span class="sxs-lookup"><span data-stu-id="0dee9-156">Working with Expressions when RDL Sandboxing is Enabled</span></span>  
 <span data-ttu-id="0dee9-157">Você pode modificar o recurso RDL Sandboxing para gerenciar os recursos que são usados por uma expressão das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="0dee9-157">You can modify the RDL Sandboxing feature to help manage the resources that are used by an expression in the following ways:</span></span>  
  
-   <span data-ttu-id="0dee9-158">Restrinja o número de caracteres que são usados para uma expressão.</span><span class="sxs-lookup"><span data-stu-id="0dee9-158">Restrict the number of characters that are used for an expression.</span></span>  
  
-   <span data-ttu-id="0dee9-159">Restrinja o tamanho do resultado retornado por uma expressão.</span><span class="sxs-lookup"><span data-stu-id="0dee9-159">Restrict the size of the result returned by an expression.</span></span>  
  
-   <span data-ttu-id="0dee9-160">Permita uma lista específica de tipos que podem ser usados em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="0dee9-160">Allow a specific list of types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="0dee9-161">Restrinja a lista de membros por nome para a lista de tipos permitidos que podem ser usados em uma expressão.</span><span class="sxs-lookup"><span data-stu-id="0dee9-161">Restrict the list of members by name for the list of allowed types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="0dee9-162">O recurso RDL Sandboxing permite criar uma lista de tipos aprovados e uma lista de membros negados.</span><span class="sxs-lookup"><span data-stu-id="0dee9-162">The RDL Sandboxing feature enables you to create a list of approved types and a list of denied members.</span></span> <span data-ttu-id="0dee9-163">A lista de tipos aprovados é chamada de lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-163">The list of approved types is called an allow list.</span></span> <span data-ttu-id="0dee9-164">A lista de membros negados é chamada de lista de contatos bloqueados.</span><span class="sxs-lookup"><span data-stu-id="0dee9-164">The list of denied members is called a block list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0dee9-165">Na definição de relatório, um computador não pode saber o tipo de todas as instâncias de uma referência de expressão.</span><span class="sxs-lookup"><span data-stu-id="0dee9-165">In the report definition, a computer cannot know the type of each instances of an expression reference.</span></span> <span data-ttu-id="0dee9-166">Quando você acrescentar um membro à lista de contatos bloqueados, estará negando todos os membros daquele nome em todos os tipos na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-166">When you add a member to the block list, you are denying all members of that name across all types in the allow list.</span></span>  
  
 <span data-ttu-id="0dee9-167">Resultados de expressão RDL são verificados em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0dee9-167">RDL expression results are verified at run time.</span></span> <span data-ttu-id="0dee9-168">Expressões RDL são verificadas na definição de relatório quando o relatório é publicado.</span><span class="sxs-lookup"><span data-stu-id="0dee9-168">RDL expressions are verified in the report definition when the report is published.</span></span> <span data-ttu-id="0dee9-169">Monitore o log de rastreamento de servidor de relatório em busca de violações.</span><span class="sxs-lookup"><span data-stu-id="0dee9-169">Monitor the report server trace log for violations.</span></span> <span data-ttu-id="0dee9-170">Para obter mais informações, consulte [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="0dee9-170">For more information, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
### <a name="working-with-types"></a><span data-ttu-id="0dee9-171">Trabalhando com tipos</span><span class="sxs-lookup"><span data-stu-id="0dee9-171">Working with Types</span></span>  
 <span data-ttu-id="0dee9-172">Quando você acrescentar um tipo à lista de permissões, estará controlando os seguintes pontos de entrada para acessar expressões RDL:</span><span class="sxs-lookup"><span data-stu-id="0dee9-172">When you add a type to the allow list, you are controlling the following entry points to access RDL expressions:</span></span>  
  
-   <span data-ttu-id="0dee9-173">Membros estáticos de um tipo.</span><span class="sxs-lookup"><span data-stu-id="0dee9-173">Static members of a type.</span></span>  
  
-   <span data-ttu-id="0dee9-174">O [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` método.</span><span class="sxs-lookup"><span data-stu-id="0dee9-174">The [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` method.</span></span>  
  
-   <span data-ttu-id="0dee9-175">O **\<Classes>** elemento na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="0dee9-175">The **\<Classes>** element in the report definition.</span></span>  
  
-   <span data-ttu-id="0dee9-176">Membros que você acrescentou à lista de contatos bloqueados para um tipo na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-176">Members that you have added to the block list for a type in the allow list.</span></span>  
  
 <span data-ttu-id="0dee9-177">A lista de permissões não controla os seguintes pontos de entrada:</span><span class="sxs-lookup"><span data-stu-id="0dee9-177">The allow list does not control the following entry points:</span></span>  
  
-   <span data-ttu-id="0dee9-178">Conjuntos de dados de relatório.</span><span class="sxs-lookup"><span data-stu-id="0dee9-178">Report datasets.</span></span> <span data-ttu-id="0dee9-179">Campos em conjuntos de dados de relatório que são retornados de consultas que possam conter algum tipo RDL válido.</span><span class="sxs-lookup"><span data-stu-id="0dee9-179">Fields in report datasets that are returned from queries might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="0dee9-180">Parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="0dee9-180">Report parameters.</span></span> <span data-ttu-id="0dee9-181">Os valores de parâmetros fornecidos pelo usuário podem conter algum tipo RDL válido.</span><span class="sxs-lookup"><span data-stu-id="0dee9-181">User-supplied parameter values might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="0dee9-182">Membros de um tipo habilitado que não estão na lista de contatos bloqueados.</span><span class="sxs-lookup"><span data-stu-id="0dee9-182">Members of an enabled type that are not in the block list.</span></span> <span data-ttu-id="0dee9-183">Por padrão, todos os membros de todos os tipos são habilitados na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-183">By default, all members of all types in the allow list are enabled.</span></span> <span data-ttu-id="0dee9-184">Quando você acrescentar um nome de membro à lista de contatos bloqueados, estará negando todos os membros com aquele nome em todos os tipos que estiverem na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-184">When you add a member name to the block list, you are denying all members with that name across all types that are in the allow list.</span></span>  
  
 <span data-ttu-id="0dee9-185">Para habilitar um membro de um tipo mas negar um membro com o mesmo nome para um tipo diferente, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dee9-185">To enable a member of one type but deny a member with the same name for a different type, you must do the following:</span></span>  
  
-   <span data-ttu-id="0dee9-186">Adicione um **\<Deny>** elemento para o nome do membro.</span><span class="sxs-lookup"><span data-stu-id="0dee9-186">Add a **\<Deny>** element for the member name.</span></span>  
  
-   <span data-ttu-id="0dee9-187">Crie um membro de proxy com um nome diferente em uma classe em um assembly personalizado para o membro que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="0dee9-187">Create a proxy member with a different name on a class in a custom assembly for the member that you want to enable.</span></span>  
  
-   <span data-ttu-id="0dee9-188">Acrescente aquela nova classe à lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-188">Add that new class to the allow list.</span></span>  
  
 <span data-ttu-id="0dee9-189">Para acrescentar funções de [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework à lista de permissões, acrescente os tipos correspondentes do namespace Microsoft.VisualBasic à lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-189">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework functions to the allow list, add the corresponding types from the Microsoft.VisualBasic namespace to the allow list.</span></span>  
  
 <span data-ttu-id="0dee9-190">Para acrescentar palavras-chave de tipo do [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework à lista de permissões, acrescente o tipo CLR correspondente à lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-190">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework type keywords to the allow list, add the corresponding CLR type to the allow list.</span></span> <span data-ttu-id="0dee9-191">Por exemplo, para usar a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] palavra-chave .NET Framework `Integer` , adicione o seguinte fragmento XML ao **\<RDLSandboxing>** elemento:</span><span class="sxs-lookup"><span data-stu-id="0dee9-191">For example, to use the [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework keyword `Integer`, add the following XML fragment to the **\<RDLSandboxing>** element:</span></span>  
  
```  
<Allow Namespace="System">Int32</Allow>  
```  
  
 <span data-ttu-id="0dee9-192">Para acrescentar um tipo genérico ou que permite valor nulo do [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework à lista de permissões, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dee9-192">To add a generic or a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type to the allow list, you must do the following:</span></span>  
  
-   <span data-ttu-id="0dee9-193">Crie um tipo de proxy para o tipo genérico ou anulável do [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0dee9-193">Create a proxy type for the generic or [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type.</span></span>  
  
-   <span data-ttu-id="0dee9-194">Acrescente um tipo de proxy à lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-194">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="0dee9-195">Acrescentar um tipo de um assembly personalizado à lista de permissões não concede implicitamente permissão de execução no assembly.</span><span class="sxs-lookup"><span data-stu-id="0dee9-195">Adding a type from a custom assembly to the allow list does not implicitly grant execute permission on the assembly.</span></span> <span data-ttu-id="0dee9-196">Você deve modificar especificamente o arquivo de segurança de acesso a código e fornecer permissão de execução ao assembly.</span><span class="sxs-lookup"><span data-stu-id="0dee9-196">You must specifically modify the code access security file and provide execute permission to your assembly.</span></span> <span data-ttu-id="0dee9-197">Para obter mais informações, veja [Segurança de acesso do código no Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="0dee9-197">For more information, see [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
#### <a name="maintaining-the-deny-list-of-members"></a><span data-ttu-id="0dee9-198">Mantendo a \<Deny> lista de membros</span><span class="sxs-lookup"><span data-stu-id="0dee9-198">Maintaining the \<Deny> List of Members</span></span>  
 <span data-ttu-id="0dee9-199">Quando você acrescentar um tipo à lista de permissões, use a lista a seguir para determinar quando você deverá atualizar a lista de membros bloqueados.</span><span class="sxs-lookup"><span data-stu-id="0dee9-199">When you add a new type to the allow list, use the following list to determine when you might have to update the block list of members:</span></span>  
  
-   <span data-ttu-id="0dee9-200">Quando você atualiza um assembly personalizado com uma versão que introduz novos tipos.</span><span class="sxs-lookup"><span data-stu-id="0dee9-200">When you update a custom assembly with a version that introduces new types.</span></span>  
  
-   <span data-ttu-id="0dee9-201">Quando você acrescenta os membros aos tipos na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-201">When you add members to the types in the allow list.</span></span>  
  
-   <span data-ttu-id="0dee9-202">Quando você atualiza o [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="0dee9-202">When you update the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] on the report server.</span></span>  
  
-   <span data-ttu-id="0dee9-203">Quando você atualiza o servidor de relatório para uma versão mais recente do [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dee9-203">When you upgrade the report server to a later version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="0dee9-204">Quando você atualiza um servidor de relatório para tratar um esquema de RDL posterior, porque novos membros podem ter sido adicionados a tipos RDL.</span><span class="sxs-lookup"><span data-stu-id="0dee9-204">When you update a report server to handle a later RDL schema, because new members might have been added to RDL types.</span></span>  
  
### <a name="working-with-operators-and-new"></a><span data-ttu-id="0dee9-205">Trabalhando com operadores e novo</span><span class="sxs-lookup"><span data-stu-id="0dee9-205">Working with Operators and New</span></span>  
 <span data-ttu-id="0dee9-206">Por padrão, os operadores de linguagem do [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework, com exceção de `New`, são sempre permitidos.</span><span class="sxs-lookup"><span data-stu-id="0dee9-206">By default, [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework language operators, except for `New`, are always allowed.</span></span> <span data-ttu-id="0dee9-207">O `New` operador é controlado pelo `AllowNew` atributo no **\<Allow>** elemento.</span><span class="sxs-lookup"><span data-stu-id="0dee9-207">The `New` operator is controlled by the `AllowNew` attribute on the **\<Allow>** element.</span></span> <span data-ttu-id="0dee9-208">Outros operadores de linguagem, como o operador de acessador de coleção padrão `!` e [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework macros de conversão, como `CInt` , são sempre permitidos.</span><span class="sxs-lookup"><span data-stu-id="0dee9-208">Other language operators, such as the default collection accessor operator `!` and [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework cast macros such as `CInt`, are always allowed.</span></span>  
  
 <span data-ttu-id="0dee9-209">Acrescentar operadores a uma lista de contatos bloqueados, incluindo operadores personalizados, não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="0dee9-209">Adding operators to a block list, including custom operators, is not supported.</span></span> <span data-ttu-id="0dee9-210">Para excluir operadores para um tipo, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dee9-210">To exclude operators for a type, you must do the following:</span></span>  
  
-   <span data-ttu-id="0dee9-211">Crie um tipo de proxy que não implementa os operadores que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0dee9-211">Create a proxy type that does not implement the operators that you want to exclude.</span></span>  
  
-   <span data-ttu-id="0dee9-212">Acrescente um tipo de proxy à lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-212">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="0dee9-213">Para criar uma nova matriz em uma expressão RDL, crie a matriz em um método em uma classe que você define e acrescente essa classe à lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-213">To create a new array in an RDL expression, create the array in a method on a class that you define, and add that class to the allow list.</span></span>  
  
 <span data-ttu-id="0dee9-214">Para criar uma nova matriz em uma expressão RDL, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0dee9-214">To create a new array in an RDL expression, you must do the following:</span></span>  
  
-   <span data-ttu-id="0dee9-215">Defina uma nova classe e crie a matriz em um método nessa classe.</span><span class="sxs-lookup"><span data-stu-id="0dee9-215">Define a new class and create the array in a method on that class.</span></span>  
  
-   <span data-ttu-id="0dee9-216">Acrescente a classe à lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="0dee9-216">Add the class to the allow list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dee9-217">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0dee9-217">See Also</span></span>  
 <span data-ttu-id="0dee9-218">[Arquivo de configuração RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="0dee9-218">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 [<span data-ttu-id="0dee9-219">Log de rastreamento do serviço Servidor de Relatório</span><span class="sxs-lookup"><span data-stu-id="0dee9-219">Report Server Service Trace Log</span></span>](report-server/report-server-service-trace-log.md)  
  
  
