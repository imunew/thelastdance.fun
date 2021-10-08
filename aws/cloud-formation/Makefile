stack-family=lastdance

deploy-s3:
	aws --profile $(profile) cloudformation deploy \
		--template ./s3.yml \
		--stack-name $(stack-family)-web-s3 \
		--parameter-overrides StackFamily=$(stack-family) \
		--capabilities CAPABILITY_IAM \
		--no-fail-on-empty-changeset

deploy-certificate:
	aws --profile $(profile) cloudformation deploy \
		--template ./certificate.yml \
		--stack-name $(stack-family)-certificate \
		--parameter-overrides StackFamily=$(stack-family) \
		--capabilities CAPABILITY_NAMED_IAM \
		--region us-east-1 \
		--no-fail-on-empty-changeset

deploy-cloud-front:
	aws --profile $(profile) cloudformation deploy \
		--template ./cloud-front.yml \
		--stack-name $(stack-family)-web-cloud-front \
		--parameter-overrides StackFamily=$(stack-family) \
		--capabilities CAPABILITY_NAMED_IAM \
		--no-fail-on-empty-changeset
