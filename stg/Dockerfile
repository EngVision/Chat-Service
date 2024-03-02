FROM rocketchat/rocket.chat:6.3.12

ENV MONGO_URL="mongodb+srv://admin:5LnPkKh2dx1JFEI6@rs0.u40wfvl.mongodb.net/rocketchat-stg?replicaSet=atlas-p1bt7l-shard-0" \
    MONGO_OPLOG_URL="mongodb+srv://admin:5LnPkKh2dx1JFEI6@rs0.u40wfvl.mongodb.net/local-stg?replicaSet=atlas-p1bt7l-shard-0" \
    ROOT_URL="http://localhost:3000" \
    PORT=3000 \
    ADMIN_USERNAME=engvision_admin \
    ADMIN_NAME="EngVision Admin" \
    ADMIN_EMAIL=engvision.dev@gmail.com \
    ADMIN_PASS=EngVision2023@ \
    OVERWRITE_SETTING_Show_Setup_Wizard=completed

EXPOSE 3000

CMD ["node", "main.js"]
