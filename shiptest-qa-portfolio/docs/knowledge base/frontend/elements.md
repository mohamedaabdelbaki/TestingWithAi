# Source element inventory

Reviewed source revision `447c72c4b4eca87f1b4906052eecb4fdd8bd6373`. This inventory gives the source location of each control, landmark, table cell and markup condition. A control can be absent or disabled at runtime. Use the linked component to read the full expression when needed.

## Components

- [routes/+layout.svelte](#routeslayoutsvelte)
- [routes/+page.svelte](#routespagesvelte)
- [routes/assistant/+page.svelte](#routesassistantpagesvelte)
- [routes/login/+page.svelte](#routesloginpagesvelte)
- [routes/register/+page.svelte](#routesregisterpagesvelte)
- [routes/shipments/+page.svelte](#routesshipmentspagesvelte)
- [routes/shipments/[id]/+page.svelte](#routesshipmentsidpagesvelte)
- [lib/components/DynamicCard.svelte](#libcomponentsdynamiccardsvelte)
- [lib/components/QacartMark.svelte](#libcomponentsqacartmarksvelte)
- [lib/components/ShipmentForm.svelte](#libcomponentsshipmentformsvelte)
- [lib/components/agent/ChatDrawer.svelte](#libcomponentsagentchatdrawersvelte)
- [lib/components/agent/Markdown.svelte](#libcomponentsagentmarkdownsvelte)
- [lib/components/cards/AdditionalOptionsCard.svelte](#libcomponentscardsadditionaloptionscardsvelte)
- [lib/components/cards/RateCard.svelte](#libcomponentscardsratecardsvelte)
- [lib/components/cards/SenderCard.svelte](#libcomponentscardssendercardsvelte)
- [lib/components/cards/ServiceSelectionCard.svelte](#libcomponentscardsserviceselectioncardsvelte)
- [lib/components/shipments/DeleteModal.svelte](#libcomponentsshipmentsdeletemodalsvelte)
- [lib/components/shipments/PromoModal.svelte](#libcomponentsshipmentspromomodalsvelte)
- [lib/components/shipments/ShipmentFilters.svelte](#libcomponentsshipmentsshipmentfilterssvelte)
- [lib/components/shipments/ShipmentsTable.svelte](#libcomponentsshipmentsshipmentstablesvelte)
- [lib/components/shipments/StatsCards.svelte](#libcomponentsshipmentsstatscardssvelte)

## routes/+layout.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| render condition | {#if isPublicRoute &#124;&#124; !data.user} | [L41](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L41) |
| render condition | {:else} | [L43](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L43) |
| aside | See component markup | [L45](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L45) |
| a | href="/" aria-label="QAcart — ShipTest home" | [L49](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L49) |
| nav | aria-label="Main" | [L77](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L77) |
| render condition | {#each navItems as item (item.href)} | [L78](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L78) |
| a | href={item.href} aria-current={isActive ? 'page' : undefined} · {item.name} | [L80](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L80) |
| button | type="button" disabled={loggingOut} disabled disabled · {loggingOut ? t('common.loading') : t('nav.logout')} | [L93](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L93) |
| main | See component markup | [L104](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L104) |
| render condition | {#if showAssistant} | [L110](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Blayout.svelte#L110) |

## routes/+page.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Bpage.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| h1 | {heading.split(' ').slice(0, -1).join(' ')} | [L30](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/%2Bpage.svelte#L30) |

## routes/assistant/+page.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| h1 | Shipping Rules | [L67](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L67) |
| form | See component markup | [L74](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L74) |
| label | for="question" · Your question | [L81](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L81) |
| input | id="question" type="text" value={question} disabled={loading} placeholder="e.g. What is the maximum weight for a Domestic shipment?" | [L82](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L82) |
| button | type="submit" disabled={loading &#124;&#124; question.trim() === ''} | [L90](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L90) |
| render condition | {#each EXAMPLES as example (example)} | [L102](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L102) |
| button | type="button" | [L103](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L103) |
| render condition | {#if loading} | [L114](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L114) |
| p | role="status" · {t('ai.thinking')} | [L115](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L115) |
| render condition | {#if errorMessage} | [L118](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L118) |
| div | role="alert" | [L119](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L119) |
| render condition | {#if answer} | [L127](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L127) |
| section | aria-label="Answer" | [L128](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L128) |
| render condition | {#if sources.length > 0} | [L133](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L133) |
| section | aria-labelledby="sources-heading" | [L134](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L134) |
| h2 | id="sources-heading" | [L135](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L135) |
| render condition | {#each sources as source (source.n)} | [L143](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/assistant/%2Bpage.svelte#L143) |

## routes/login/+page.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| h1 | {t('auth.loginTitle')} | [L54](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L54) |
| form | See component markup | [L59](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L59) |
| render condition | {#if errorMessage} | [L60](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L60) |
| div | role="alert" | [L61](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L61) |
| label | for="email" · {t('auth.email')} | [L71](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L71) |
| input | id="email" name="email" type="email" required value={email} placeholder={t('placeholders.enterEmail')} | [L74](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L74) |
| label | for="password" · {t('auth.password')} | [L87](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L87) |
| input | id="password" name="password" type="password" required value={password} placeholder={t('placeholders.enterPassword')} | [L90](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L90) |
| button | type="submit" disabled={loading} · {loading ? t('common.loading') : t('auth.login')} | [L103](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L103) |
| a | href="/register" · {t('auth.registerHere')} | [L114](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/login/%2Bpage.svelte#L114) |

## routes/register/+page.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| h1 | {t('auth.registerTitle')} | [L65](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L65) |
| form | See component markup | [L70](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L70) |
| render condition | {#if errorMessage} | [L71](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L71) |
| div | role="alert" | [L72](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L72) |
| fieldset | See component markup | [L80](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L80) |
| legend | Account Information | [L81](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L81) |
| label | for="email" · {t('auth.email')} | [L84](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L84) |
| input | id="email" type="email" required value={form.email} | [L87](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L87) |
| label | for="password" · {t('auth.password')} | [L97](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L97) |
| input | id="password" type="password" required value={form.password} | [L100](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L100) |
| label | for="confirmPassword" · Confirm Password | [L110](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L110) |
| input | id="confirmPassword" type="password" required value={form.confirmPassword} placeholder="Re-enter your password" | [L116](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L116) |
| fieldset | See component markup | [L129](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L129) |
| legend | Personal Information | [L130](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L130) |
| label | for="fullName" · {t('auth.fullName')} | [L136](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L136) |
| input | id="fullName" type="text" name required value={form.fullName} | [L139](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L139) |
| label | for="phone" · {t('auth.phone')} | [L149](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L149) |
| input | id="phone" type="tel" required value={form.phone} | [L152](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L152) |
| label | for="country" · {t('auth.country')} | [L162](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L162) |
| select | id="country" required value={form.country} | [L165](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L165) |
| option | value="" · {t('placeholders.selectCountry')} | [L171](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L171) |
| render condition | {#each countriesData.countries as country (country.code)} | [L172](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L172) |
| option | value={country.name} · {country.name} | [L173](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L173) |
| label | for="city" · {t('auth.city')} | [L178](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L178) |
| input | id="city" type="text" required value={form.city} | [L181](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L181) |
| label | for="postalCode" · {t('auth.postalCode')} | [L190](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L190) |
| input | id="postalCode" type="text" required value={form.postalCode} | [L193](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L193) |
| label | for="street" · {t('auth.street')} | [L203](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L203) |
| input | id="street" type="text" required value={form.street} | [L206](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L206) |
| button | type="submit" disabled={loading} · {loading ? t('common.loading') : t('auth.register')} | [L218](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L218) |
| a | href="/login" · {t('auth.loginHere')} | [L229](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/register/%2Bpage.svelte#L229) |

## routes/shipments/+page.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%2Bpage.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| h1 | My | [L78](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%2Bpage.svelte#L78) |
| a | href="/" · + Create Shipment | [L81](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%2Bpage.svelte#L81) |
| render condition | {#if showSuccess} | [L89](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%2Bpage.svelte#L89) |
| div | role="status" | [L90](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%2Bpage.svelte#L90) |
| render condition | {#if errorMessage} | [L98](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%2Bpage.svelte#L98) |
| div | role="alert" | [L99](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%2Bpage.svelte#L99) |
| div | aria-busy={working} | [L116](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%2Bpage.svelte#L116) |

## routes/shipments/[id]/+page.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| a | href="/shipments" · ← Back to Shipments | [L68](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L68) |
| h1 | {isDraft ? &#96;Draft Shipment #${shipment.id}&#96; : shipment.trackingNumber} | [L74](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L74) |
| render condition | {#if isDraft} | [L83](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L83) |
| a | href="/?edit={shipment.id}" · Edit | [L87](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L87) |
| button | type="button" disabled={working} · {working ? 'Finalizing...' : 'Finalize Shipment'} | [L93](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L93) |
| render condition | {:else} | [L101](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L101) |
| a | href="/?repeat={shipment.id}" · Repeat | [L107](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L107) |
| button | type="button" disabled={working} · Delete | [L114](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L114) |
| render condition | {#if errorMessage} | [L126](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L126) |
| div | role="alert" | [L127](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L127) |
| section | aria-labelledby="sender-heading" | [L136](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L136) |
| h2 | id="sender-heading" · Sender Information | [L140](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L140) |
| section | aria-labelledby="receiver-heading" | [L162](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L162) |
| h2 | id="receiver-heading" · Receiver Information | [L166](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L166) |
| section | aria-labelledby="package-heading" | [L188](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L188) |
| h2 | id="package-heading" · Package Details | [L192](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L192) |
| render condition | {#if shipment.package.description} | [L210](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L210) |
| section | aria-labelledby="service-heading" | [L219](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L219) |
| h2 | id="service-heading" · Service &amp; Options | [L223](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L223) |
| render condition | {#if options.length === 0} | [L240](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L240) |
| render condition | {:else} | [L242](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L242) |
| render condition | {#each options as option (option.label)} | [L244](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L244) |
| section | aria-labelledby="cost-heading" | [L255](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L255) |
| h2 | id="cost-heading" · Cost Details | [L259](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L259) |
| render condition | {#each costLines as line (line.label)} | [L265](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/shipments/%5Bid%5D/%2Bpage.svelte#L265) |

## lib/components/DynamicCard.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| fieldset | disabled | [L61](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L61) |
| legend | See component markup | [L69](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L69) |
| render condition | {#if title.toLowerCase().includes('sender')} | [L71](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L71) |
| render condition | {:else if title.toLowerCase().includes('receiver')} | [L73](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L73) |
| render condition | {:else if title.toLowerCase().includes('package')} | [L75](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L75) |
| render condition | {:else} | [L77](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L77) |
| render condition | {#if shipmentType} | [L82](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L82) |
| render condition | {#if !rules} | [L87](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L87) |
| render condition | {:else} | [L91](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L91) |
| render condition | {#each fieldEntries as [name, field] (name)} | [L93](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L93) |
| render condition | {#if rule.type === 'checkbox'} | [L100](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L100) |
| input | type="checkbox" id={name} name checked={!!formData[name]} | [L102](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L102) |
| label | for={name} · {rule.label} | [L111](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L111) |
| render condition | {:else} | [L120](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L120) |
| label | for={name} · {rule.label}               {#if rule.required} | [L121](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L121) |
| render condition | {#if rule.required} | [L123](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L123) |
| render condition | {#if rule.type === 'number' && rule.validation?.max} | [L127](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L127) |
| render condition | {#if rule.type === 'select'} | [L134](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L134) |
| select | id={name} name value | [L135](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L135) |
| option | value="" · {rule.placeholder &#124;&#124; 'Select...'} | [L147](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L147) |
| render condition | {#each rule.options ?? [] as option (option.value)} | [L148](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L148) |
| option | value={option.value} · {option.label} | [L149](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L149) |
| render condition | {:else if rule.type === 'number'} | [L152](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L152) |
| input | type="number" id={name} name value | [L153](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L153) |
| render condition | {:else} | [L170](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L170) |
| input | type="text" id={name} name value | [L171](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L171) |
| render condition | {#if error} | [L187](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L187) |
| p | id="{name}-error" role="alert" · {error} | [L188](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/DynamicCard.svelte#L188) |

## lib/components/QacartMark.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/QacartMark.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| Shared rendering | See full source for rendered Markdown or branding. | [Source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/QacartMark.svelte) |

## lib/components/ShipmentForm.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| form | See component markup | [L48](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L48) |
| render condition | {#if state.submitError} | [L55](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L55) |
| div | role="alert" | [L56](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L56) |
| render condition | {#if state.errors.general} | [L64](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L64) |
| div | role="alert" | [L65](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L65) |
| render condition | {#if state.errors.service} | [L109](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L109) |
| p | role="alert" · {state.errors.service} | [L110](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L110) |
| button | type="button" · state.submit(true)}       disabled={state.loading}       class="btn"     > | [L129](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L129) |
| button | type="submit" disabled={state.loading} | [L139](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/ShipmentForm.svelte#L139) |

## lib/components/agent/ChatDrawer.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| render condition | {#if !open} | [L117](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L117) |
| button | type="button" | [L118](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L118) |
| render condition | {:else} | [L126](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L126) |
| div | role="dialog" aria-label={t('ai.title')} | [L127](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L127) |
| h2 | See component markup | [L133](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L133) |
| button | type="button" · (open = false)}         aria-label={t('ai.closeChat')}         class="text-muted-foreground hover:text-foreground transition-colors"       > | [L137](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L137) |
| div | role="log" aria-live="polite" aria-label="Conversation" | [L147](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L147) |
| render condition | {#if messages.length === 0 && !loading} | [L154](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L154) |
| render condition | {#each messages as message, i (i)} | [L158](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L158) |
| div | role | [L159](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L159) |
| div | role | [L165](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L165) |
| render condition | {#if message.role === 'user'} | [L171](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L171) |
| render condition | {:else} | [L173](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L173) |
| render condition | {#if message.toolCalls?.length} | [L178](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L178) |
| render condition | {#each message.toolCalls as call, j (j)} | [L181](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L181) |
| render condition | {#if message.proposal} | [L193](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L193) |
| render condition | {#each Object.entries(message.proposal.values) as [name, value] (name)} | [L197](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L197) |
| render condition | {#if Object.keys(message.proposal.violations).length > 0} | [L205](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L205) |
| p | role="alert" · {Object.values(message.proposal.violations).join(' ')} | [L206](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L206) |
| render condition | {#if message.applied} | [L211](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L211) |
| p | role="status" | [L212](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L212) |
| render condition | {:else} | [L216](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L216) |
| button | type="button" · applyProposal(i)}>                   Apply to form | [L217](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L217) |
| render condition | {#if message.latencyMs !== undefined} | [L224](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L224) |
| render condition | {#if loading} | [L230](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L230) |
| p | role="status" · {t('ai.thinking')} | [L231](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L231) |
| render condition | {#if errorMessage} | [L234](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L234) |
| p | role="alert" · {errorMessage} | [L235](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L235) |
| label | for="agent-message" · {t('ai.placeholder')} | [L245](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L245) |
| textarea | id="agent-message" value={input} placeholder={t('ai.placeholder')} disabled={loading} | [L246](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L246) |
| button | type="button" disabled={loading &#124;&#124; input.trim() === ''} aria-label={t('ai.send')} | [L255](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/ChatDrawer.svelte#L255) |

## lib/components/agent/Markdown.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/Markdown.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| Shared rendering | See full source for rendered Markdown or branding. | [Source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/agent/Markdown.svelte) |

## lib/components/cards/AdditionalOptionsCard.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| fieldset | disabled | [L27](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L27) |
| legend | See component markup | [L32](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L32) |
| render condition | {#if !rules} | [L37](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L37) |
| render condition | {:else} | [L41](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L41) |
| render condition | {#each checkboxes as { name, field } (name)} | [L43](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L43) |
| input | type="checkbox" id={name} checked={!!formData[name]} | [L46](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L46) |
| label | for={name} · {field.label} | [L55](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L55) |
| render condition | {#if field.disabled} | [L61](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L61) |
| render condition | {#if pickupField} | [L68](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L68) |
| fieldset | See component markup | [L69](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L69) |
| legend | {pickupField.label} | [L70](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L70) |
| render condition | {#each pickupField.options ?? [] as option (option.value)} | [L74](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L74) |
| input | type="radio" id="pickup-{option.value}" name="pickupMethod" value={option.value} checked={formData.pickupMethod === option.value} | [L78](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L78) |
| label | for="pickup-{option.value}" · {option.label} | [L89](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L89) |
| render condition | {#if optionDisabled} | [L97](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/AdditionalOptionsCard.svelte#L97) |

## lib/components/cards/RateCard.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/RateCard.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| section | aria-labelledby="rate-heading" disabled | [L28](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/RateCard.svelte#L28) |
| h2 | id="rate-heading" | [L34](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/RateCard.svelte#L34) |
| render condition | {#if rateBreakdown} | [L57](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/RateCard.svelte#L57) |
| render condition | {#each lines as line (line.label)} | [L63](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/RateCard.svelte#L63) |
| render condition | {#if calculatedPrice === null} | [L72](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/RateCard.svelte#L72) |

## lib/components/cards/SenderCard.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/SenderCard.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| section | See component markup | [L10](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/SenderCard.svelte#L10) |
| section | aria-labelledby="sender-heading" | [L13](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/SenderCard.svelte#L13) |
| h2 | id="sender-heading" · {t('form.senderInformation')} | [L19](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/SenderCard.svelte#L19) |

## lib/components/cards/ServiceSelectionCard.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| fieldset | disabled | [L24](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L24) |
| legend | See component markup | [L29](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L29) |
| render condition | {#if !serviceRules} | [L34](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L34) |
| render condition | {:else if serviceRules.services?.length === 0} | [L38](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L38) |
| p | role="status" · No service can carry this package. Reduce the weight to see options. | [L39](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L39) |
| render condition | {:else} | [L42](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L42) |
| render condition | {#each serviceRules.services ?? [] as service (service.id)} | [L44](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L44) |
| label | checked disabled | [L46](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L46) |
| input | type="radio" name="serviceType" value={service.id} checked disabled | [L52](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/cards/ServiceSelectionCard.svelte#L52) |

## lib/components/shipments/DeleteModal.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/DeleteModal.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| render condition | {#if open} | [L31](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/DeleteModal.svelte#L31) |
| div | role="alertdialog" aria-modal="true" aria-labelledby="delete-title" aria-describedby="delete-description" | [L33](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/DeleteModal.svelte#L33) |
| h2 | id="delete-title" · Delete Shipment | [L48](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/DeleteModal.svelte#L48) |
| p | id="delete-description" · Are you sure you want to delete this shipment? This action cannot be undone. | [L52](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/DeleteModal.svelte#L52) |
| button | type="button" · Cancel | [L56](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/DeleteModal.svelte#L56) |
| button | type="button" · Delete | [L63](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/DeleteModal.svelte#L63) |

## lib/components/shipments/PromoModal.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/PromoModal.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| render condition | {#if show} | [L22](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/PromoModal.svelte#L22) |
| div | role="dialog" aria-modal="true" aria-labelledby="promo-title" | [L24](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/PromoModal.svelte#L24) |
| h2 | id="promo-title" · Special Offer! | [L35](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/PromoModal.svelte#L35) |
| button | type="button" · (show = false)}         class="btn btn-primary text-sm"       >         Close | [L37](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/PromoModal.svelte#L37) |

## lib/components/shipments/ShipmentFilters.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| label | for="status-filter" · Status | [L18](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L18) |
| select | id="status-filter" value={statusFilter} · onStatusChange(e.currentTarget.value)}         class="field"       > | [L21](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L21) |
| option | value="all" · All Statuses | [L27](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L27) |
| option | value="draft" · Draft | [L28](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L28) |
| option | value="finalized" · Finalized | [L29](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L29) |
| label | for="type-filter" · Type | [L34](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L34) |
| select | id="type-filter" value={typeFilter} · onTypeChange(e.currentTarget.value)}         class="field"       > | [L37](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L37) |
| option | value="all" · All Types | [L43](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L43) |
| option | value="Domestic" · Domestic | [L44](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L44) |
| option | value="IntraGulf" · Intra-Gulf | [L45](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L45) |
| option | value="International" · International | [L46](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentFilters.svelte#L46) |

## lib/components/shipments/ShipmentsTable.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| render condition | {#if shipments.length === 0} | [L72](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L72) |
| h2 | {t('table.noShipments')} | [L74](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L74) |
| a | href="/" · + {t('table.createShipment')} | [L77](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L77) |
| render condition | {:else} | [L85](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L85) |
| table | See component markup | [L87](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L87) |
| caption | Your shipments | [L88](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L88) |
| th | See component markup | [L91](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L91) |
| th | {t('table.trackingNumber')} | [L94](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L94) |
| th | Sender | [L100](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L100) |
| th | Receiver | [L106](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L106) |
| th | Destination | [L112](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L112) |
| th | Type | [L118](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L118) |
| th | {t('table.status')} | [L124](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L124) |
| render condition | {#each shipments as shipment (shipment.id)} | [L133](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L133) |
| td | See component markup | [L135](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L135) |
| button | type="button" | [L136](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L136) |
| render condition | {#if openMenuId === shipment.id} | [L147](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L147) |
| div | role="menu" aria-label="Actions for {label(shipment)}" | [L148](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L148) |
| a | role="menuitem" href="/shipments/{shipment.id}" | [L154](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L154) |
| render condition | {#if shipment.status === 'draft'} | [L163](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L163) |
| a | role="menuitem" href="/?edit={shipment.id}" | [L164](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L164) |
| button | role="menuitem" type="button" | [L172](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L172) |
| render condition | {:else} | [L184](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L184) |
| a | role="menuitem" href="/?repeat={shipment.id}" | [L185](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L185) |
| button | role="menuitem" type="button" | [L195](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L195) |
| th | {shipment.status === 'draft' ? '-' : shipment.trackingNumber} | [L211](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L211) |
| td | {shipment.from.name} | [L214](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L214) |
| td | {shipment.to.name} | [L215](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L215) |
| td | {shipment.to.city}, {shipment.to.country} | [L216](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L216) |
| td | {t(&#96;shipmentTypes.${shipment.service.shipmentType}&#96;)} | [L219](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L219) |
| td | {#if shipment.status === 'draft'} | [L222](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L222) |
| render condition | {#if shipment.status === 'draft'} | [L223](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L223) |
| render condition | {:else} | [L229](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/ShipmentsTable.svelte#L229) |

## lib/components/shipments/StatsCards.svelte

[Full source](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/StatsCards.svelte)

| Element | Attributes, label, or condition | Source |
| --- | --- | --- |
| render condition | {#each stats as stat (stat.label)} | [L13](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/components/shipments/StatsCards.svelte#L13) |

## Exact English text

Use [translations.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/lib/translations.ts) for translation keys and the relevant rule JSON for generated labels.
