<template>
	<div>
		<div class="center examplex">
			<vs-navbar target-scroll="#padding-scroll-content" padding-scroll center-collapsed v-model="active">
				<template #left>
					<img src="/logo2.png" alt="" />
				</template>
				<vs-navbar-item :active="active == 'guide'" id="guide">
					Guide
				</vs-navbar-item>
				<vs-navbar-item :active="active == 'docs'" id="docs">
					Documents
				</vs-navbar-item>
				<vs-navbar-item :active="active == 'components'" id="components">
					Components
				</vs-navbar-item>
				<vs-navbar-item :active="active == 'license'" id="license">
					license
				</vs-navbar-item>
				<template #right>
					<vs-button @click="active3 = !active3">Get Started</vs-button>
				</template>
			</vs-navbar>
			<div id="padding-scroll-content" class="square">
				<div class="child">
					child 1
				</div>
				<div class="child">
					child 2
				</div>
				<div class="child">
					child 3
				</div>
			</div>
		</div>
		<template>
			<div class="center">
				<vs-button border @click="active3 = !active3">
					Prompt
				</vs-button>
				<vs-dialog width="300px" not-center not-close v-model="active3">
					<template #header>
						<h4 class="not-margin">Welcome what is your <b>Name</b></h4>
					</template>

					<div class="con-content">
						<vs-input v-model="name" placeholder="Name"></vs-input>
					</div>

					<template #footer>
						<div class="con-footer">
							<vs-button @click="active3 = false" transparent>
								Ok
							</vs-button>
						</div>
					</template>
				</vs-dialog>
			</div>
		</template>
	</div>
</template>

<script>
export default {
	data: () => ({
		active: "guide",
		active2: false,
		active3: false,
		name: ""
	})
};
</script>

<style lang="stylus">
getColor(vsColor, alpha = 1)
    unquote("rgba(var(--vs-"+vsColor+"), "+alpha+")")
getVar(var)
    unquote("var(--vs-"+var+")")
.con-footer
  display flex
  align-items center
  justify-content flex-end
  .vs-button
    margin 0px
    .vs-button__content
      padding 10px 30px
    ~ .vs-button
      margin-left 10px
.not-margin
  margin 0px
  font-weight normal
  padding 10px
  padding-bottom 0px
.con-content
  width 100%
  p
    font-size .8rem
    padding 0px 10px
  .vs-checkbox-label
    font-size .8rem
  .vs-input-parent
    width 100%
  .vs-input-content
    margin 10px 0px
    width calc(100%)
    .vs-input
      width 100%
.footer-dialog
  display flex
  align-items center
  justify-content center
  flex-direction column
  width calc(100%)
  .new
    margin 0px
    margin-top 20px
    padding: 0px
    font-size .7rem
    a
      color getColor('primary') !important
      margin-left 6px
      &:hover
        text-decoration underline
  .vs-button
    margin 0px
</style>
